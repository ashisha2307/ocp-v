# VM teamplate for bulk provisioning test

```bash
$ oc process --parameters example-demo-rehl9-32x12 -n openshift
```

```bash
$ oc process example-demo-rehl9-32x12 -n openshift -p NAME=NAME_ARG -p CORE=CORE_ARG -p NETWORK_NAME=NW_NAME_ARG -p MEM=MEM_ARGGi -p IPADDRESS=ADDRESS_ARG | oc apply -f -
```

*Example*
```bash
oc process example-demo-rehl9-32x12 -n openshift -p NAME=test1 -p CORE=1 -p NETWORK_NAME=vm-network -p MEM=10Gi -p IPADDRESS=192.168.100.1 | oc apply -f -
oc process example-demo-rehl9-32x12 -n openshift -p NAME=test2 -p CORE=1 -p NETWORK_NAME=vm-network -p MEM=10Gi -p IPADDRESS=192.168.100.2 | oc apply -f -
oc process example-demo-rehl9-32x12 -n openshift -p NAME=test3 -p CORE=1 -p NETWORK_NAME=vm-network -p MEM=10Gi -p IPADDRESS=192.168.100.3 | oc apply -f -
oc process example-demo-rehl9-32x12 -n openshift -p NAME=test4 -p CORE=1 -p NETWORK_NAME=vm-network -p MEM=10Gi -p IPADDRESS=192.168.100.4 | oc apply -f -

```
Where we want integer (i.e core, sockets, thread),  double parenthesis + setting the value as a a string (i.e. putting it inside quotation marks).

```yaml
kind: Template
apiVersion: template.openshift.io/v1
metadata:
  name: example-demo-rehl9-32x12
  namespace: openshift
  uid: 2fff508f-7875-4b9a-a625-813f8f909635
  resourceVersion: '51352206'
  creationTimestamp: '2024-10-24T17:03:19Z'
  labels:
    app.kubernetes.io/part-of: hyperconverged-cluster
    template.kubevirt.io/version: v0.29.2
    app.kubernetes.io/version: 4.16.3
    template.kubevirt.io/type: vm
    vm.kubevirt.io/template: example-demo-rehl9
    app.kubernetes.io/component: templating
    app.kubernetes.io/managed-by: ssp-operator
    flavor.template.kubevirt.io/medium: 'true'
    os.template.kubevirt.io/rhel9.0: 'true'
    os.template.kubevirt.io/rhel9.1: 'true'
    app.kubernetes.io/name: custom-templates
    os.template.kubevirt.io/rhel9.2: 'true'
    os.template.kubevirt.io/rhel9.3: 'true'
    os.template.kubevirt.io/rhel9.4: 'true'
    vm.kubevirt.io/template.namespace: openshift
    os.template.kubevirt.io/rhel9.5: 'true'
  annotations:
    template.kubevirt.io/provider: Example Demo
    template.kubevirt.io/containerdisks: |
      registry.redhat.io/rhel9/rhel-guest-image
    template.kubevirt.io/version: v1alpha1
    openshift.io/display-name: Example REL 9 VM
    openshift.io/documentation-url: 'https://github.com/kubevirt/common-templates'
    template.kubevirt.io/images: |
      https://access.redhat.com/downloads/content/479/ver=/rhel---9/9.0/x86_64/product-software
    operator-sdk/primary-resource-type: SSP.ssp.kubevirt.io
    defaults.template.kubevirt.io/disk: rootdisk
    name.os.template.kubevirt.io/rhel9.0: Red Hat Enterprise Linux 9.0 or higher
    name.os.template.kubevirt.io/rhel9.1: Red Hat Enterprise Linux 9.0 or higher
    template.kubevirt.io/editable: |
      /objects[0].spec.template.spec.domain.memory.guest
      /objects[0].spec.template.spec.domain.devices.disks
      /objects[0].spec.template.spec.volumes
      /objects[0].spec.template.spec.networks
    name.os.template.kubevirt.io/rhel9.2: Red Hat Enterprise Linux 9.0 or higher
    template.openshift.io/bindable: 'false'
    openshift.kubevirt.io/pronounceable-suffix-for-name-expression: 'true'
    operator-sdk/primary-resource: openshift-cnv/ssp-kubevirt-hyperconverged
    name.os.template.kubevirt.io/rhel9.3: Red Hat Enterprise Linux 9.0 or higher
    name.os.template.kubevirt.io/rhel9.4: Red Hat Enterprise Linux 9.0 or higher
    tags: 'hidden,kubevirt,virtualmachine,linux,rhel'
    name.os.template.kubevirt.io/rhel9.5: Red Hat Enterprise Linux 9.0 or higher
    template.kubevirt.io/provider-support-level: Full
    description: Demo Template for Example
    openshift.io/support-url: 'https://github.com/kubevirt/common-templates/issues'
    iconClass: icon-rhel
    openshift.io/provider-display-name: Example
  managedFields:
    - manager: Mozilla
      operation: Update
      apiVersion: template.openshift.io/v1
      time: '2024-10-24T17:03:19Z'
      fieldsType: FieldsV1
      fieldsV1:
        'f:metadata':
          'f:annotations':
            'f:template.kubevirt.io/editable': {}
            'f:operator-sdk/primary-resource': {}
            'f:operator-sdk/primary-resource-type': {}
            'f:defaults.template.kubevirt.io/disk': {}
            'f:template.kubevirt.io/provider-support-level': {}
            'f:name.os.template.kubevirt.io/rhel9.0': {}
            'f:description': {}
            'f:name.os.template.kubevirt.io/rhel9.1': {}
            'f:template.openshift.io/bindable': {}
            'f:name.os.template.kubevirt.io/rhel9.2': {}
            'f:name.os.template.kubevirt.io/rhel9.3': {}
            'f:iconClass': {}
            'f:openshift.kubevirt.io/pronounceable-suffix-for-name-expression': {}
            'f:name.os.template.kubevirt.io/rhel9.4': {}
            'f:name.os.template.kubevirt.io/rhel9.5': {}
            'f:tags': {}
            .: {}
            'f:template.kubevirt.io/provider': {}
            'f:template.kubevirt.io/containerdisks': {}
            'f:openshift.io/support-url': {}
            'f:openshift.io/provider-display-name': {}
            'f:template.kubevirt.io/images': {}
            'f:openshift.io/display-name': {}
            'f:template.kubevirt.io/version': {}
            'f:openshift.io/documentation-url': {}
          'f:labels':
            'f:os.template.kubevirt.io/rhel9.0': {}
            'f:os.template.kubevirt.io/rhel9.1': {}
            'f:os.template.kubevirt.io/rhel9.2': {}
            'f:os.template.kubevirt.io/rhel9.3': {}
            'f:vm.kubevirt.io/template.namespace': {}
            'f:app.kubernetes.io/managed-by': {}
            'f:os.template.kubevirt.io/rhel9.4': {}
            'f:os.template.kubevirt.io/rhel9.5': {}
            'f:flavor.template.kubevirt.io/medium': {}
            'f:app.kubernetes.io/name': {}
            .: {}
            'f:app.kubernetes.io/part-of': {}
            'f:app.kubernetes.io/version': {}
            'f:template.kubevirt.io/type': {}
            'f:vm.kubevirt.io/template': {}
            'f:template.kubevirt.io/version': {}
            'f:app.kubernetes.io/component': {}
        'f:objects': {}
        'f:parameters': {}
objects:
  - apiVersion: kubevirt.io/v1
    kind: VirtualMachine
    metadata:
      annotations:
        vm.kubevirt.io/validations: |
          [
            {
              "name": "minimal-required-memory",
              "path": "jsonpath::.spec.domain.memory.guest",
              "rule": "integer",
              "message": "This VM requires more memory.",
              "min": 1610612736
            }
          ]
      labels:
        app: '${NAME}'
        kubevirt.io/dynamic-credentials-support: 'true'
        vm.kubevirt.io/template: example-demo-rehl9
        vm.kubevirt.io/template.revision: '1'
        vm.kubevirt.io/template.namespace: openshift
      name: '${NAME}'
    spec:
      dataVolumeTemplates:
        - apiVersion: cdi.kubevirt.io/v1beta1
          kind: DataVolume
          metadata:
            name: '${NAME}'
          spec:
            sourceRef:
              kind: DataSource
              name: '${DATA_SOURCE_NAME}'
              namespace: '${DATA_SOURCE_NAMESPACE}'
            storage:
              resources:
                requests:
                  storage: 30Gi
      running: true
      template:
        metadata:
          annotations:
            vm.kubevirt.io/flavor: medium
            vm.kubevirt.io/os: rhel9
            vm.kubevirt.io/workload: server
          labels:
            kubevirt.io/domain: '${NAME}'
            kubevirt.io/size: medium
        spec:
          architecture: amd64
          domain:
            cpu:
              cores: ${{CORE}}
              sockets: ${{SOCKETS}}
              threads: ${{THREADS}}
            devices:
              disks:
                - disk:
                    bus: virtio
                  name: rootdisk
                - disk:
                    bus: virtio
                  name: cloudinitdisk
              interfaces:
                - bridge: {}
                  model: virtio
                  name: default
                - masquerade: {}
                  model: virtio
                  name: podnetwork
              rng: {}
            features:
              smm:
                enabled: true
            firmware:
              bootloader:
                efi: {}
            memory:
              guest: '${MEM}'
          networks:
            - multus:
                networkName: '${NETWORK_NAME}'
              name: default
            - name: podnetwork
              pod: {}
          terminationGracePeriodSeconds: 180
          volumes:
            - dataVolume:
                name: '${NAME}'
              name: rootdisk
            - cloudInitNoCloud:
                networkData: |
                  version: 2
                  ethernets:
                    eth0:
                      addresses:
                        - ${IPADDRESS}/${SUBNET}
                      gateway4: ${GATEWAY}
                      nameservers:
                        addresses:
                          - ${DNS1}
                          - ${DNS2}
                userData: |-
                  #cloud-config
                  user: cloud-user
                  password: ${CLOUD_USER_PASSWORD}
                  chpasswd: { expire: False }
              name: cloudinitdisk
parameters:
  - name: CORE
    description: number of core
    value: '1'
  - name: SOCKETS
    description: number of socket
    value: '1'
  - name: THREADS
    description: number of thread
    value: '1'
  - name: MEM
    description: memory size
    value: '12Gi'
  - name: NETWORK_NAME
    description: NAD name
    value: vm-network
  - name: IPADDRESS
    description: VM ip address
    value: 10.205.129.51
  - name: SUBNET
    description: VM subnet
    value: '24'
  - name: GATEWAY
    description: VM gateway
    value: 10.205.129.254
  - name: DNS1
    description: VM DNS1
    value: 10.105.133.210
  - name: DNS2
    description: VM DNS1
    value: 10.13.22.7
  - name: NAME
    description: VM name
    generate: expression
    from: 'rhel9-[a-z0-9]{16}'
  - name: DATA_SOURCE_NAME
    description: Name of the DataSource to clone
    value: rhel9
  - name: DATA_SOURCE_NAMESPACE
    description: Namespace of the DataSource
    value: openshift-virtualization-os-images
  - name: CLOUD_USER_PASSWORD
    description: Randomized password for the cloud-init user cloud-user
    generate: expression
    from: '[a-z0-9]{4}-[a-z0-9]{4}-[a-z0-9]{4}'

```
