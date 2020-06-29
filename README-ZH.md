[![PyPI](https://img.shields.io/pypi/v/napalm-huawei-vrp.svg)](https://pypi.python.org/pypi/napalm-huawei-vrp)
[![PyPI](https://img.shields.io/pypi/dm/napalm-huawei-vrp.svg)](https://pypi.python.org/pypi/napalm-huawei-vrp)

# napalm-h3c-cmw [English](README.md)

NAPALM华三系列comware设备，如S5560，FW1070.


## 介绍

这个驱动目前支持以下功能

* get_facts():  获取设备基础信息
* cli(): 发送任何命令到设备中
* get_lldp_neighbors(): 获取LLDP邻居信息
* get_config(): 获取配置信息
* is_active(): 设备是否可用
* ping(): 从设备中ping远端设备
* get_arp_table(): 获取设备APR表
* get_mac_address_table(): 获取设备MAC地址表
* get_interfaces(): 获取接口信息
* get_interfaces_ip(): 获取接口IP信息
* get_interfaces_counters(): 获取接口统计信息

## 如何安装

使用PIP来安装napalm-h3c-cmw

`pip install napalm-h3c-cmw`

## 快速开始

```python
from napalm import get_network_driver
driver = get_network_driver('h3c_cmw')
device = driver(hostname='192.168.76.10', username='admin', password='this_is_not_a_secure_password')
device.open()

get_facts = device.get_facts()
print(get_facts)

send_command = device.cli(['dis ver', 'dis cu'])
```