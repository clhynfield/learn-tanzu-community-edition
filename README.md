# Learn Tanzu Community Edition

For rationale, see [[Why we test-drive third-party software]] and [Charters: Exploratory Testing… and Beyond](https://medium.com/product-labs/charters-exploratory-testing-and-beyond-87315184f256#.1ssbkbhqn%22%20target=%22_blank%22%20rel=%22noopener%20noreferrer%22)

## Charter

Explore **Tanzu Community Edition** (TCE)  
With **iPad/MacBook** and **GCP**  
To discover **TCE's value proposition** and **intended behaviors**  

## Experience log

DuckDuckGo finds [Tanzu Community Edition](https://tanzucommunityedition.io)

The hero on the TCE main page advertises

> **Experience VMware Tanzu now**
> VMware Tanzu Community Edition is a full-featured, easy-to-manage Kubernetes platform for learners and users, especially those working in small-scale or preproduction environments

So TCE is for learners – we're in the right place! Also note that TCE is for small-scale or pre-prod, assuming not for mission-critical production use at scale.

Two buttons to engage, [TRY IT OUT][try] and [DOWNLOAD][dl].

### Download

Note that the downloads are either source, or pre-compiled binaries for macOS/amd64 (no Apple silicon support), Linux/amd64, and Windows/amd64. In the charter, we set out to explore from Mac or iPad, so if we download, we should probably choose to do so from a Linux VM in GCP.

### Try It Out!

> Tanzu Community Edition enables the creation of modern application platforms. These platforms can be created on local laptops or various cloud and infrastructure options. A platform deployed using Tanzu Community Edition provides a Kubernetes runtime, tooling, and additional repository of packages that can be installed/updated very easily. Tanzu Community Edition is a freely available and community-supported. The platform itself consists of various open source software components to enable various functions.

The proposed scope's intended behavior, then, should cover

- Kubernetes runtime
- tooling
- additional repository of packages

And already, some explicit behavior to test for:

> packages that can be installed/updated very easily

Further…

> What you will do in the lab:
>
> - Familiarize with Tanzu CLI
> - Deploy Modern Apps
> - Scale Applications
> - Monitor Applications

According to the workshop page, this should only take fifteen minutes – perfect to fit within a pomodoro!

Login is required, but fortunately it allows login with GitHub! (Requires granting read-only access to the GitHub user's email) Hmm, and then it requires local registration with Tanzu Developer Center….

…And registration fails in Private Browsing mode with a 403 – CSRF missing.

…And allowing cross-site tracking yields `misdirected request to "tce-workshops-w01-s3269.tce-vmworld.tanzu-dev.com"`.

End of pomodoro!
***

### And we're in!

One or both of these might have been transient, as trying the same thing again brings me to a working workshop!

> Tanzu Community Edition is already deployed and running on the environment. To see various options execute below

```shell-history
[~] $ tanzu
Tanzu CLI

Usage:
  tanzu [command]

Available command groups:

  Admin
    builder                 Build Tanzu components

  Run
    cluster                 Kubernetes cluster operations
    conformance             Run Sonobuoy conformance tests against clusters
    kubernetes-release      Kubernetes release operations
    management-cluster      Kubernetes management cluster operations
    package                 Tanzu package management
    standalone-cluster      Create clusters without a dedicated management cluster

  System
    completion              Output shell completion code
    config                  Configuration for the CLI
    init                    Initialize the CLI
    login                   Login to the platform
    plugin                  Manage CLI plugins
    update                  Update the CLI
    version                 Version information


Flags:
  -h, --help   help for tanzu

Use "tanzu [command] --help" for more information about a command.

Not logged in
```

The workshop explains that there are two methods to building Kubernetes-centric platforms – building workload clusters separate from a management cluster, or just building a standalone cluster. It doesn't explain *why*, but I intimate it might have something to do with the trade-off between separation of concerns and getting going with minimal time and resources.

### Sidebar: Who's this for?

Between pomodoros, I was reflecting on user-centered design, and I thought it might be instructive to refine the charter a bit – if that's a thing, refining the charter after exploration has begun? – to discover *who* the value proposition of TCE is addressing. That might actually be at least strongly implicit in "value proposition", and I hope it's not stretching too far.


[try]: https://tanzu.vmware.com/developer/workshops/lab-tce-deploy/ (Deploying Apps and Microservices with Tanzu Community Edition)
[dl]: https://tanzucommunityedition.io/download/ (Download – tanzucommunityedition.io)

