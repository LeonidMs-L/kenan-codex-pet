---
name: install-conan-pet
description: Install or restore the bundled 名侦探柯南 v2 skin as a local custom pet in the Codex desktop app on Windows. Use when the user asks to add or reinstall this specific skin.

---

# 安装名侦探柯南皮肤

将 `install-conan-pet` 整个目录解压到用户的 `.agents/skills` 目录，再在 Codex 中发送 `$install-conan-pet 安装柯南皮肤`。

从本技能目录运行 `scripts/install.ps1`。在本地 Windows PowerShell 中调用脚本，脚本会校验随包提供的皮肤，并将其写入当前用户的 Codex 宠物目录。用户如果明确给出其他 Codex 根目录，将绝对路径传给 `-CodexDirectory`。

读取脚本返回的 `status`、`directory` 和 `local_pet_id`。`installed` 表示已复制，`already-installed` 表示目录中已有相同版本。遇到同名目录冲突时，保留现有文件并报告冲突。

运行完成后，告诉用户可以在 Codex 桌面端的「设置 → 宠物」点击「刷新」，然后选中「名侦探柯南」。只有看到了桌面端的宠物列表时，才报告已在界面验证。

`assets/conan-detective` 也可以作为一个完整的本地宠物目录，手动复制到 Codex 根目录下的 `pets`。它包含原始透明 PNG 动画图集和 v2 清单。



<img src="./conan-preview.gif" width="480" alt="演示动图">
