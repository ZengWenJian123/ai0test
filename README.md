# GMI 非晶材料 ELN（实验室电子记录）

这是一个面向 **GMI 非晶材料制备工艺（熔炼 → 拉丝 → 退火 → 检测）** 的 ELN 可视化原型。

## 目前支持的核心能力

- 数据可视化分析：工艺趋势、GMI 对比、退火温度相关性、SPC 控制图、缺陷率趋势
- **CSV 上传导入入口**：从页面直接上传 `.csv` 导入
- **手工填写入口**：在页面中填写批次与参数后直接追加记录
- **CSV 表头自动识别**：支持中英文常见列名自动映射（如 `batch_id/batch/批次`）
- **按实验分类保存**：按 `实验编号` 保存为独立数据集，可切换查看
- 数据本地持久化：使用 `localStorage` 保存实验数据

## 快速启动

```bash
python3 -m http.server 8080
```

浏览器访问：

- `http://localhost:8080/dashboard/index.html`

## CSV 字段（标准目标字段）

- `batch_id`: 批次编号
- `melt_temp_c`: 熔炼温度（℃）
- `draw_speed_mps`: 拉丝速度（m/s）
- `anneal_temp_c`: 退火温度（℃）
- `gmi_ratio_pct`: GMI 指标（%）
- `defect_rate_pct`: 缺陷率（%）

> 如果 CSV 采用其他常见表头（中英文、大小写、下划线差异），页面会尝试自动识别并映射。
