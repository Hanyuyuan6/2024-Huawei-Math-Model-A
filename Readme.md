# 2024 年中国研究生数学建模竞赛 A 题：风电场有功功率优化调度

本仓库保存参赛团队针对 A 题四个问题编写的 MATLAB 代码与可公开的派生结果。

> 隐私与权利边界：竞赛题面、官方附件、原始数据和提交模板不再随仓库分发。它们可能包含第三方权利或本机 Office 元数据，并且未发现允许长期公开再分发的明确许可。请从竞赛官方渠道取得文件，并阅读 [THIRD_PARTY_DATA.md](THIRD_PARTY_DATA.md)。

## 环境

- MATLAB R2024a。
- 部分脚本需要 Optimization Toolbox、Statistics and Machine Learning Toolbox、Signal Processing Toolbox 或 Econometrics Toolbox；请按 MATLAB 报错安装缺失组件。
- 脚本使用自身位置解析输入路径，不依赖 Windows 盘符，也可在 macOS/Linux MATLAB 中运行。

## 准备官方输入

从竞赛官方渠道取得下列文件，并放入 `Math_Model/`：

- `附件1-疲劳评估数据.xls`
- `附件2-风电机组采集数据.mat`
- `附件3-噪声和延迟作用下的采集数据.mat`
- `附件4-噪声和延迟作用下的采集数据.xlsx`

这些路径已加入 `.gitignore`，不会被意外提交。参考文件名、来源说明和本次清理前样本的 SHA-256 见 [THIRD_PARTY_DATA.md](THIRD_PARTY_DATA.md)。附件 5/6 属于提交输出或模板，也不会进入 Git。

## 代码结构

- `Math_Model/question_1/question_1.m`：问题一，雨流计数与疲劳损伤评估。
- `Math_Model/question_2/question_2.m`：问题二核心模型。
- `Math_Model/question_2/question_2_tradition.m`：问题二物理机理对照。
- `Math_Model/question_2/Ct_Cp_model_from_Q2.m`：训练并保存 `Cp`/`Ct` 回归模型。
- `Math_Model/question_2/for_save.m`：生成扭矩与推力结果。
- `Math_Model/question_3/question_3.m`：问题三优化调度。
- `Math_Model/question_3/question_3_local_OPT.m`：问题三局部最优对照。
- `Math_Model/question_4/question_4.m`：问题四噪声与延迟条件下的调度。
- `Math_Model/question_4/Calcul_state_transfer.m`：计算状态转移矩阵。
- `Math_Model/question_4/PCA_for_weight.m`：估计累积疲劳损伤权重。
- `Math_Model/question_4/compare_in_different_condition.m`：比较不同条件下的表现。

## 建议运行顺序

在 MATLAB 中将仓库设为当前工程或执行：

```matlab
repo_root = pwd;
addpath(genpath(fullfile(repo_root, 'Math_Model')));
```

随后按题目顺序运行脚本。问题三和问题四会使用问题二生成的 `mdl_Cp.mat`、`mdl_Ct.mat` 与 `feature_mean_std.mat`。问题四还会使用状态转移矩阵。脚本现在从 `Math_Model/` 解析这些输入，而不是依赖当前工作目录。

## 数据注意事项

- 加载附件 3 后，请确认工作区变量名为 `data_TS_WF_noise`；若官方文件版本不同，以实际变量名为准。
- 大型 `.mat` 文件未纳入仓库。不要把本地数据、答案表、缓存或 Office 临时文件强制加入 Git。
- 历史提交可能仍包含已删除的第三方文件或机器路径；在历史重写完成前，旧提交仍可访问这些内容。

## 权利说明

仓库当前没有为作者代码授予开源许可。第三方竞赛材料不属于本仓库授权范围。详见 [NOTICE.md](NOTICE.md)。
