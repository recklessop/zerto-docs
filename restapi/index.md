# Introduction to the Zerto Virtual Replication RESTFUL APIs

The Zerto Virtual Replication RESTful API enables you to manage Zerto Virtual Replication programmatically. The REST APIs provide a way to automate many of the tasks required to manage DR, without having to use the Zerto User Interface. For related documentation, refer to myZerto > [Technical Documentation](https://www.zerto.com/myzerto/technical-documentation/)

# Using the APIs

All APIs are exposed over HTTPS.

Most of the Zerto Virtual Replication RESTful APIs require a session running with basic authorization. The username and password authorization used must be a valid username and password either for the Windows machine where the Zerto Virtual Manager is installed or for the hypervisor manager, VMware vCenter Server or Microsoft SCVMM, accessed by the Zerto Virtual Manager. In both cases the Zerto Virtual Manager is the Zerto Virtual Manager where the APIs will run.

The following APIs can be called without any authentication:

- Listing the RESTful APIs, described in Listing the Available APIs and “/v1/ API”, on page 29.
- Getting help for an API, described in Getting Help for an API.
- Generating a resource report about the virtual machines being protected to a recovery site, using the ResourcesReport API, described in “Managing vCD APIs”, on page 247.

When passing a URL in a browser, you require a security certificate. In Microsoft Internet Explorer you have to be in Compatibility mode.

To test the APIs, Zerto recommends using a REST client, such as the following:

- For Google Chrome: [Postman](http://www.getpostman.com/)
- For Microsoft Internet Explorer and Mozilla FireFox: [RESTClient](http://www.restclient.org)

## Starting a Session

Using the username and password either for the Windows machine where the Zerto Virtual Manager is installed or for the hypervisor manager, VMware vCenter Server or Microsoft SCVMM, accessed by the Zerto Virtual Manager, you can establish a session by posting the following URL:

```http
https://zvm_ip:port/v1/session/add
```

A session identifier, x-zerto-session, is returned as part of the response header and the session is established. The session identifier is used in the client code with every API call for the duration of the session.

The APIs can be consumed by applications implemented in different technologies in a stateless manner.
Data returned is formatted either as JSON or as XML as set by the consumer. By default, data that is returned for the v1 APIs is formatted as JSON.



# Managing VPGs

