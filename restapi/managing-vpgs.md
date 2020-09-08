# Managing VPGs

The Zerto Virtual Replication RESTful APIs includes an API that enables you to manage the creation and editing of VPGs programmatically.

## An Introduction to the vpgSettings API

You can manage VPGs using both the /v1/vpgs API or the /v1/vpgSettings API. Use the /v1/vpgs API to perform actions on a VPG, such as failing over a VPG, cloning a VPG or testing a VPG. Use the /v1/vpgSettings API to manage the definition of a VPG, including editing the VPG definition and adding or removing virtual machines from a VPG.
Use the vpgSettings API to do the following:

- Create a new VPG.
- Display values in an existing VPG.
- Edit existing values in a VPG.

### What is Supported

The vpgSettings API works in the following environments:

- vCenter Server
- Hyper-V
- vCenter Server to Hyper-V and Hyper-V to vCenter Server
- vCloud Director to vCloud Director
- Running on the protected site
- Running on the recovery site
- Preseeding
- Virtual machines with RDM disks

### What is Not Supported

The vpgSettings API does not support the following:

- Setting backup
- AWS
- Azure

## How Does the vpgSettings API Work
The definition of a VPG can be described by the set of values. The vpgSettings API enables managing this set of values. All the VPG settings are managed in a VPG settings object, which is saved in memory. This object is managed during a session and used to either create a VPG or update an existing VPG.
Managing a VPG using the vpgSettings API involves the following steps:

1. Create a VPG settings object.
1. Manipulate the VPG settings object to include the values you want.
1. Commit the VPG settings object to update the VPG definition in the Zerto Virtual Manager using the values from the VPG settings object in the memory.

The VPG settings object uses an identifier, the vpgSettingsIdentifier. This identifier is not the same as the VPG identifier used to identify an existing VPG.

To ensure uniqueness, you supply identifiers to the vpgSettings API and not names. To retrieve identifiers to use in the vpgSettings API, use other Zerto Virtual Replication RESTful APIs. For example, to retrieve the recovery network identifiers for failover and failover test networks, use the `virtualizationsites/{SITEIDENTIFIER}/networks` API to return both the network names and identifiers. In the vpgSettings API, you use the network identifier and not the name. In the same way, use the `virtualizationsites/{SITEIDENTIFIER}/vms` API to return the identifiers of all unprotected virtual machines in a site, and use these identifiers in the vpgSettings API to specify the virtual machines to add to a VPG or to protect in a new VPG.

> [!Note]
> For details about using all the Zerto Virtual Replication APIs, refer to the Zerto Virtual Replication RESTful API Reference Guide documentation.

## Using the vpgSettings API

The vpgSettings API is exposed over HTTPS and requires a session running with basic authorization. The username and password authorization used must be a valid username and password either for the Windows machine where the Zerto Virtual Manager is installed or for the hypervisor manager, VMware vCenter Server or Microsoft SCVMM, accessed by the Zerto Virtual Manager. In both cases the Zerto Virtual Manager is the Zerto Virtual Manager where the APIs will run.

Using the username and password either for the Windows machine where the Zerto Virtual Manager is installed or for the hypervisor manager, VMware vCenter Server or Microsoft SCVMM, accessed by the Zerto Virtual Manager, you can establish a session by posting the following URL:

```http
https://zvm_ip:port/v1/session/add
```

A session identifier, x-zerto-session, is returned as part of the response header and the session is established. The session identifier is used in the client code with every API call for the duration of the session.

The APIs can be consumed by applications implemented in different technologies in a stateless manner.

Data returned is formatted either as JSON or as XML as set by the consumer. By default, data that is returned for the v1 APIs is formatted as JSON.

An API session times out after 30 minutes of inactivity. A VPG settings object is automatically deleted from memory in the following situations:

- When a session times out.
- When the VPG settings object is not used in a session for 30 minutes, even if the session is still active.
- When the VPG settings object is committed.
 
