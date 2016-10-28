# Dataloop


This role installs and configures the dataloop.io agent to send
metrics back to dataloop.io.

To install from Galaxy:

```ansible-galaxy install dataloop.dataloop-agent```

## Role Variables

* `dataloop_api_key` - API key to use for the agent registration
* `dataloop_manage_service` - Enable/disable the service handler (**true**)



## Usage

In order to automatically add a node to dataloop, create a file in
your ansible repo named `group_vars/dataloop` using ansible-vault.

Make sure the file has the following content:

```yaml
---
dataloop_api_key: <insert_dataloop_api_key_here>
```

And optionally the startup tags below:

```yaml
---
dataloop_tags: <insert_csv_list_of_tags_here>
```

Additionally you can override agent name with:

```yaml
---
dataloop_agent_name: <agent_name>
```

If it's not set the hostname will be used instead.



Now ensure that your nodes are members of the "dataloop" group in your
inv/hosts file and run ansible. The dataloop client should be
installed automatically and your nodes should start showing up in the
dataloop web interface.
