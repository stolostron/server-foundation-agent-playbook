---
name: Server Foundation Error Log Collecting
description: Collect the error logs of the specified components.
example: "egent: collect import-controller err log, kubeconfig path ~/Downloads/server-foundation-sno-lite-rhrhr-kubeconfig.yaml"
parameters:
  components:
    description: Name of the components to collect the error logs
  kubeconfig_path:
    description: Path to the kubeconfig file
dependencies:
  - knowledge/acm/sf-deployments.md
---

The goal is to collect the error logs of the specified components.

If the {{components}} are not specified, collect the error logs of all the server foundation components.

The process is as follows:

- Set KUBECONFIG to the {{kubeconfig_path}}
- For each component in the {{components}} list, map the component to the namespace/deployment in the `Server Foundation Deployments` table.
- For each namespace/deployment, run `oc get pods -n <namespace> -o jsonpath='{.items[?(@.metadata.labels.app==\"<deployment>\")].metadata.name}'` to get the pod name.
- For each pod, run `oc logs <pod_name> --all-containers=true --tail=100` to get the most recent 100 lines of logs.
  (Note: it's better to create a script to automate the log collection process to avoid too many times tool calls)
- If the log contains error logs, such PANIC, "ERROR", "FATAL", "CRITICAL", collect the log.
  - Note: ignore a specific error type: `the object has been modified; please apply your changes to the latest version and try again`.
- Finally, return a report in the following way:

If no error logs are found, return with a message "No error logs found".

If error logs are found, return with the error logs.

<report>

There are error logs in the following N components:

Component: <component_name1>

Error Logs:

<error_log_1>
<error_log_2>
<error_log_3>

---

Component: <component_name2>

Error Logs:

<error_log_1>
<error_log_2>
<error_log_3>

...

</report>
