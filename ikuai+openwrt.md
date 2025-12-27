# ikuai&openwrt 回路测试

> **测试日期**：2025-12-25
> **测试环境**：PVE+ikuai+openwrt 环路测试
> **当前状态**：🟢 已通过 / 🟡 调试中 / 🔴 失败

---

## ikuai的dns设置
dhcp服务器设置时，dns必须都设置成ikuai的lan口，否则dns加速功能不能很好地使用。
比如主dns为lan口地址，副dns为公共dns，那么勾选dns加速不能完全生效，只有主副dns都设置为lan口地址，dns加速才会有用
而ikuai的dns加速只有客户端的dns设置为lan口地址时才有用，因此如果ikuai的dhcp设置的dns不都是lan口地址时，意味着客户端只有一半的解析的速度会分流给ikuai，也会很慢。

所以两个dns地址可以都设置为IKUAI的lan口地址，或者直接设置两个公共dns地址，实测两个公共dns的速度最快

