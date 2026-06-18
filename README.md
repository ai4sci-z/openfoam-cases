# openfoam-cases

OpenFOAM 典型算例复现笔记与配置文件。

## 算例列表

| 目录 | 求解器 | 问题 |
|------|--------|------|
| `lid-driven-cavity/` | `icoFoam` | 方腔驱动流，Re=100/400/1000 |
| `cylinder-flow/` | `simpleFoam` | 圆柱绕流，Re=40，验证 Strouhal 数 |
| `backward-step/` | `simpleFoam` | 后向台阶分离流，与实验数据对比 |

## 环境

OpenFOAM v10（Ubuntu 22.04 推荐）

```bash
# 安装（Ubuntu）
sudo sh -c "wget -O - https://dl.openfoam.org/gpg.key | apt-key add -"
sudo add-apt-repository http://dl.openfoam.org/ubuntu
sudo apt install openfoam10
source /opt/openfoam10/etc/bashrc
```

## 运行方式（以 lid-driven-cavity 为例）

```bash
cd lid-driven-cavity
blockMesh
icoFoam
paraFoam   # 可视化
```

## 学习笔记

每个案例目录下有 `notes.md`，记录：
- 边界条件设置思路
- 网格无关性验证
- 与理论/实验结果对比
- 常见报错与解决方法
