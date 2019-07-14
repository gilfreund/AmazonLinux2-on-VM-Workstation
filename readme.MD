Amazon Linux can be installed and used on-premise on various virtualiztion platforms.

However, in release [2.0.20190612](https://cdn.amazonlinux.com/os-images/2.0.20190612/) there is an issue with the definition of the SCSI controller which causes an issue in installing on VMware workstation. The fix is in the amzn2-vmware_esx-2.0.20190313-x86_64.xfs.gpt.ovf, specificali in the line:
```      <Item>
        <rasd:Address>0</rasd:Address>
        <rasd:Description>SCSI Controller</rasd:Description>
        <rasd:ElementName>SCSI Controller 0</rasd:ElementName>
        <rasd:InstanceID>4</rasd:InstanceID>
        <rasd:ResourceSubType>lsilogic</rasd:ResourceSubType>
        <rasd:ResourceType>6</rasd:ResourceType>
</Item>```
Since this will change the sha1 signature of the file, I have attached the updated manifest file. Also included are the [cloud-init](https://cloudinit.readthedocs.io/en/latest/) files I am using.


Link:
[Running Amazon Linux 2 as a Virtual Machine On-Premises](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/amazon-linux-2-virtual-machine.html)
