# Zerto Technical Documentation

## What is Zerto Virtual Replication

Zerto Virtual Replication provides a business continuity (BC) and disaster recovery (DR) solution in a virtual environment, providing near real-time replication, with write-order fidelity, with minimal impact on product workloads. Fully automated orchestration delivers failover, failback, and reverse protection in one click. Non-disruptive disaster recovery testing gives you confidence that your DR solution will work predictably and consistently. Consistency groups ensure all virtual machines that comprise an application are protected in the exact same manner no matter where they are in the environment.

With support for different hypervisors such as vSphere or Hyper-V, and public cloud sites such as Azure, workloads can be protected, migrated, and recovered, either within the same hypervisor environment or across hypervisor environments.

Zerto Virtual Replication is installed in both the protected and the recovery sites. The disaster recovery across these sites is managed by a browser-based user interface. Managing Zerto Virtual Replication is also possible programmatically, either via a set of REST-ful APIs or PowerShell cmdlets. Recovery that does rely on native replication functionality, such as recovery available with Microsoft Active Directory or SQL Server, can also be replicated using Zerto Virtual Replication, and whether the native replication functionality is used or not is determined by site considerations, such as increased complexity of having multiple points of control and possible additional costs incurred when using vendor native replication.

You configure replication by first pairing the site with the virtual machines to be protected, with a recovery site. You then define what virtual machines you want replicated in consistency groups, where the virtual machines in a group comprise the application and data you want to protect. You can group different virtual machines together or keep them separate. By creating different replication groups, you can customize the replication requirements for each group to better optimize the recovery plan.

Disaster recovery is based on the premise that you will want to recover with a minimum RPO. However, to enable full recovery in cases such as virus attacks, Zerto Virtual Replication provides the ability to recover to a point in time up to 30 days prior to the disaster. When recovery earlier than 30 days is required, Zerto Virtual Replication provides an extended recovery, using a Long Term Retention process mechanism that enables you to recover to a recovery site based on daily, weekly or monthly retention sets, going as far back as a year. The majority of the processing for both disaster recovery and extended recovery is done at the recovery site, minimizing the impact on the production site.

## Support

Zerto delivers enterprise-class support services that are built into all of our products. These services include real time alerts when RPO/ RTO targets are not being met, network degradation alarms and reminders to check configurations and Virtual Protection Groups. Zerto solutions are also backed by global support service centers that provide on-demand access to an expert team of support engineers.

### myZerto

Using the portal, Zerto customers can:

- Download the latest version of Zerto Virtual Replication
- Find answers to common question in the Zerto knowledge base
- Connect with the Zerto community on our forums
- Follow the status of open support cases

New to myZerto?
Request a [Log-in](https://www.zerto.com/myzerto/login-request/)

Existing Support User?
Log-in to [myZerto](https://www.zerto.com/myzerto/)

### Contact Zerto Support

- Report a new case directly from your ZVR GUI
- Submit a support case at [https://www.zerto.com/myzerto/support/](https://www.zerto.com/myzerto/support/)
- For immediate assistance on a live Severity-1 production issue call the Zerto Support Line in your area

  - United States +1-866-271-3145
  - United Kingdom +44-800-088-5495
  - Canada +1-866-271-3145
  - Australia +61-1800-466-227
  - China +86-400-120-8535
  - Germany +49-32221090005

- Below numbers are only available locally.

  - China +10-800-713-1114(N)
  - China +10-800-130-1074(S)
  - Germany +0800-184-4995
  - Indonesia +001-803-015-203-9790
  - Taiwan +00801-14-7242
  - South Korea +003-0813-1992
  - India +000-800-100-4056
  - Japan +0800-111-9335
  - Hong Kong +800-905-393
  - Singapore +800-492-2306

## Contributing to Zerto Docs

- Submit a pull request
- open an issue