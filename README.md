# OpenShift Quickstarts

Centralized repository of community quickstarts that anyone can import into their OpenShift deployments.

## Objective

With the addition of [Quick starts to OpenShift](https://docs.openshift.com/container-platform/4.7/web_console/creating-quick-start-tutorials.html) we want to curate a place for people to create and contribute quick starts to use for their deployments that may not be included in an operator.

## OCP QuickStart Ideas

Please add to the list here of quickstarts that would be helpful.

| Quickstart                   | Details                                                       |
|------------------------------|---------------------------------------------------------------|
| Authentication via HTPasswd  | oc create authentication_configuration/htpasswd_auth.yaml     |
| Authentication Configuration | How to Configure oauth ldap etc                               |
| OCP-Virt port mapping        | How to open SSH or RDP to a vm)                               |
| Alert customizations         | editing alert bodies, customize or create new alerts          |
| MTV (Konveyor)               | How to: Move vms from vmware, Move vms across storage devices |
| OCP-Virt Connect to BMC      | (Bare Metal Controller ie. iLO, Drac, etc)                    |
| Create storage class         | How to create a storage class                                 |
| Secrets and use cases        |                                                               |

Please do a pull request to the repository or put in an issue and we will add to the list.

## Quick Starts

| Quickstart                  | To install clone this repository and run the below command |
|-----------------------------|------------------------------------------------------------|
| Authentication via HTPasswd | oc create authentication_configuration/htpasswd_auth.yaml  |

## Quick Example on how to create a Quick Start

### Prerequisites

You must have cluster administrator privileges.

### Procedure

To create a new quick start, run:

```shell
oc get -o yaml consolequickstart spring-with-s2i > my-quick-start.yaml
```

Run:

```shell
oc create -f my-quick-start.yaml
```

Update the YAML file using the guidance outlined in [this documentation](https://docs.openshift.com/container-platform/4.7/web_console/creating-quick-start-tutorials.html).

Save your edits.

To quickly test the quickstart go into developer on and click the `+Add` button in the left menu. You should see quickstarts in the top left box.

### Tips

For testing you will need to delete and apply the CRD and reapply it:

```shell
oc delete consolequickstarts htpasswd-auth -n <namespace>
```

Re-apply:

```shell
oc create -f my-quick-start.yaml
```

To get a list of all quickstarts:

```shell
oc get consolequickstarts
```
