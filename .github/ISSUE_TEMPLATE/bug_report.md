---
name: Bug report
about: Create a report to help us improve Mountpoint for S3 CSI Driver
labels: 

---

/kind bug
> **_NOTE:_**  If this is a filesystem related bug, please take a look at the [Mountpoint repo](https://github.com/awslabs/mountpoint-s3) to submit a [bug report](https://github.com/awslabs/mountpoint-s3/issues/new?assignees=&labels=bug&projects=&template=bug-report.yml)

**What happened?**

**What you expected to happen?**

**How to reproduce it (as minimally and precisely as possible)?**

**Anything else we need to know?**:


name: Bug report
description: File a bug report for Mountpoint for Amazon S3 CSI Driver
labels: ["bug"]
body:
  - type: markdown
    attributes:
      value: |
        Thanks for taking the time to fill out a bug report.
  - type: markdown
    attributes:
      value: |
        **Note: security issues should not be reported here.** Please follow the [security policy for this repository](https://github.com/awslabs/mountpoint-s3-csi-driver/security/policy).
  - type: markdown
    attributes:
      value: |
        ### Before opening a new bug report...

        * Is this bug related to Mountpoint's CSI Driver or Mountpoint itself? If it's the latter, you may be better served by [opening a bug report against Mountpoint](https://github.com/awslabs/mountpoint-s3/issues/new?assignees=&labels=bug&projects=&template=bug-report.yml).
  - type: input
    id: kubernetes-version
    attributes:
      label: Kubernetes version
      description: |
        Which version of Kubernetes are you using? Please use `kubectl version`.
        If you're using a Kubernetes-like implementation (like K3s or minikube), please mention this.
    validations:
      required: true
  - type: input
    id: csi-driver-version
    attributes:
      label: CSI Driver version
      description: |
        Which version of the Mountpoint for Amazon S3 CSI Driver are you using?
        If you're building from source or a fork, please state that.
    validations:
      required: true
  - type: input
    id: region
    attributes:
      label: AWS Region
      description: Which AWS region did you experience the bug in?
      placeholder: us-west-2
    validations:
      required: false
  - type: textarea
    id: environment
    attributes:
      label: Describe the running environment
      description: |
        What else can you tell us about the environment you\'re running the project? For example:
        * Is this running on Amazon EKS or a self-managed Kubernetes cluster?
        * What credentials are you using? IRSA credentials, or something else?
        * What operating system are you using for your Kubernetes nodes?
        * Any other details about your environment?
      placeholder: Running with EKS on Amazon Linux 2 nodes, with credentials provided using IRSA. My workload runs against an S3 bucket in the same AWS account.
    validations:
      required: true
  - type: textarea
    id: expected-behavior
    attributes:
      label: What did you expect to happen?
      description: What happened? Why did you expect this behavior?
    validations:
      required: true
  - type: textarea
    id: actual-behavior
    attributes:
      label: What actually happened?
      description: Please include as many details as you can to help us understand the problem. There's an area for log output later also.
      placeholder: The CSI driver failed to mount my file system with error X.
    validations:
      required: true
  - type: textarea
    id: anything-else
    attributes:
      label: Anything else we need to know?
      description: |
        Use this to share any details which you think may be relevant, but you haven't had the opportunity to share in the form yet. 
    validations:
      required: false
