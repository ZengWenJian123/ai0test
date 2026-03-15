# GMI 非晶材料 ELN（实验室电子记录）

这是一个面向 **GMI 非晶材料制备工艺（熔炼 → 拉丝 → 退火 → 检测）** 的 ELN 可视化原型。

## 实验数据可视化分析能力

当前看板（`dashboard/index.html`）提供：

- 工艺时序趋势（熔炼温度、拉丝速度、退火温度）
- 批次 GMI 指标柱状对比（自动按均值高亮）
- 参数-性能相关性散点图（退火温度 vs GMI）
- GMI 控制图（X-bar + UCL/LCL）
- 缺陷率趋势图（带阈值线）
- 顶部统计卡片（批次数、平均 GMI、平均缺陷率、最佳批次）
- 批次区间筛选（起始/结束批次联动刷新）

## 数据读取方式

优先读取：`../data/sample_experiment_data.csv`（在 `/dashboard/index.html` 访问场景）。

看板内置了多路径尝试与自动回退策略；如果 CSV 加载失败（例如文件路径或静态服务配置问题），会自动切换为内置样例数据并在界面提示。

## 快速启动

```bash
python3 -m http.server 8080
```

浏览器访问：

- `http://localhost:8080/dashboard/index.html`

## 数据字段说明

示例数据位于 `data/sample_experiment_data.csv`：

- `batch_id`: 批次编号
- `melt_temp_c`: 熔炼温度（℃）
- `draw_speed_mps`: 拉丝速度（m/s）
- `anneal_temp_c`: 退火温度（℃）
- `gmi_ratio_pct`: GMI 指标（%）
- `defect_rate_pct`: 缺陷率（%）
