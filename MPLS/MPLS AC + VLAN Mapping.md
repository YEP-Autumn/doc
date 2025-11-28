# MPLS AC + VLAN Mapping



## 基本概念



## 工作机制

### MPLS AC 模式

Ethernet 模式

Ethernet + etree-leaf 模式

Ethernet + vlan-operation-table 模式

vlan 模式

vlan + bundling 模式

vlan + etree-leaf 模式

vlan + vlan-operation-table 模式

vlan + bundling + etree-leaf 模式

vlan + bundling + vlan-operation-table 模式

vlan + bundling + etree-leaf + vlan-operation-table 模式

vlan + etree-leaf + vlan-operation-table 模式

vlan + cvlan 模式

vlan + cvlan + bundling 模式

vlan + cvlan + etree-leaf 模式

vlan + cvlan + vlan-operation-table 模式

vlan + cvlan + bundling + etree-leaf 模式

vlan + cvlan + bundling + vlan-operation-table 模式

vlan + cvlan + bundling + etree-leaf + vlan-operation-table 模式

vlan + cvlan + etree-leaf + vlan-operation-table 模式

##### 功能

cvlan：配合vlan能够匹配携带指定双层vlan tag的报文

bundling：使用bundling后，在接口上能够匹配多个vlan tag

etree-leaf：配置接口为etree模式中的leaf节点，leaf节点和leaf节点间不能通信。pw必须使能controller-word

vlan-operation-table：可以增加对报文的编辑能力，ethernet支持push







## 软件设计

vlan mapping 使用的scl资源

- ingress 0 ：port_svlan hash lookup
- ingress 1 ：port_2vlan hash lookup
- egress ：无



flex qinq 使用的scl资源

- ingress 0 ：port_svlan hash lookup
- ingress 1 ：port_2vlan hash lookup
- egress 0 ：port_2vlan hash lookup
- egress 1 ：port_svlan hash lookup



mpls ac 使用的scl资源

- ingress 1：port_svlan 或者 port_2vlan hash lookup
  - 当使用 vlan + cvlan 时，使用port_2vlan
  - 其他情况使用port_svlan









*****

- MPLS 有哪些位置设置了 port scl property 属性，关联上层的哪些配置？
  - 
- 
- 









*****



#### 相关问题

- mpls-vpls stp l2protocol 透传原理
  - 是将BPDU报文的action行为改为Forward，从而使BPDU报文通过命中SCL进而转发到VPLS隧道中。











