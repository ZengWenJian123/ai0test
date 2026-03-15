# GMI 非晶材料 ELN（实验室电子记录）

这是一个面向 **GMI 非晶材料制备工艺（熔炼 → 拉丝 → 退火 → 检测）** 的 ELN 原型项目。

## 新增：实验数据可视化分析模块

本次新增了一个轻量级可视化看板（`dashboard/index.html`），用于展示典型的工艺与质量分析场景：

- 工艺时序趋势（熔炼温度、拉丝速度、退火温度）
- 批次质量柱状对比（GMI 指标）
- 参数-性能相关性散点图（退火温度 vs GMI）
- 质量控制图（X-bar，均值+控制上/下限）

## 快速启动

```bash
cd dashboard
python3 -m http.server 8080
```

然后浏览器访问：

- `http://localhost:8080`

## 数据说明

示例数据位于 `data/sample_experiment_data.csv`，字段包括：

- `batch_id`: 批次编号
- `melt_temp_c`: 熔炼温度（℃）
- `draw_speed_mps`: 拉丝速度（m/s）
- `anneal_temp_c`: 退火温度（℃）
- `gmi_ratio_pct`: GMI 指标（%）
- `defect_rate_pct`: 缺陷率（%）

该数据可作为后续接入真实 ELN 数据库与设备采集数据的模板。
