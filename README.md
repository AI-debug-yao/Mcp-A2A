# MCP (Model Context Protocol) 项目示例

本项目展示了 MCP (Model Context Protocol) 的多种应用场景，包括 Agent-to-Agent (A2A) 通信、地图助手、文本分析等功能。

## 项目结构

```
MCP/
├── A2A/                    # Agent-to-Agent 通信示例
│   ├── WeatherAgent.py     # 天气查询服务（FastAPI）
│   ├── BasketBallAgent.py  # 篮球安排智能体
│   └── requirements.txt    # 依赖包
├── demo1/                  # MCP 助手示例 1
│   ├── assistant_mcp_amap_bot.py    # 高德地图智能助手
│   ├── assistant_mcp_txt_bot.py     # 文本计数智能助手
│   ├── txt_counter.py      # 文本计数服务
│   ├── 旅行规划.md         # 旅行规划表设计提示词
│   ├── .env                # 环境变量配置
│   └── requirements.txt    # 依赖包
└── demo2/                  # MCP 助手示例 2
    ├── assistant_bot.py    # 多功能 AI 助手
    ├── .env                # 环境变量配置
    └── requirements.txt    # 依赖包
```

## 模块说明

### A2A - Agent-to-Agent 通信

**WeatherAgent.py**
- 基于 FastAPI 的天气查询服务
- 提供 Agent Card 端点 (`/.well-known/agent.json`)
- 处理天气查询任务
- 运行在端口 8000

**BasketBallAgent.py**
- 篮球活动安排智能体
- 通过 A2A 协议与 WeatherAgent 通信
- 根据天气条件决定是否安排篮球活动

**依赖安装**
```bash
cd A2A
pip install -r requirements.txt
```

**运行示例**
```bash
# 启动天气服务
python WeatherAgent.py

# 在另一个终端运行篮球安排
python BasketBallAgent.py
```

### demo1 - MCP 助手示例

**assistant_mcp_amap_bot.py**
- 基于 Qwen Agent 的高德地图助手
- 支持地图查询、路线规划、景点推荐
- 提供三种运行模式：GUI、TUI、测试模式

**assistant_mcp_txt_bot.py**
- 文本分析智能助手
- 支持字符数、单词数、行数统计
- 提供三种运行模式

**依赖安装**
```bash
cd demo1
pip install -r requirements.txt
```

**运行示例**
```bash
# 运行地图助手（GUI 模式）
python assistant_mcp_amap_bot.py

# 运行文本计数助手（GUI 模式）
python assistant_mcp_txt_bot.py
```

### demo2 - 多功能 AI 助手

**assistant_bot.py**
- 集成高德地图、网页抓取、Bing 搜索的多功能助手
- 基于 Qwen Agent 框架
- 支持多种 MCP 工具

**依赖安装**
```bash
cd demo2
pip install -r requirements.txt
```

**运行示例**
```bash
python assistant_bot.py
```

## 技术栈

- **LLM 框架**: qwen_agent
- **Web 框架**: FastAPI, Uvicorn
- **MCP 协议**: mcp
- **API 服务**: DashScope (通义千问)
- **地图服务**: 高德地图 (AMAP)

## 环境配置

需要配置以下环境变量（在 `.env` 文件中）：
```
DASHSCOPE_API_KEY=your_api_key_here
DASHSCOPE_TIMEOUT=30
AMAP_MAPS_API_KEY=your_amap_key_here
```

## 功能特性

1. **A2A 通信**: 智能体之间通过标准化协议通信
2. **地图助手**: 地点查询、路线规划、旅游推荐
3. **文本分析**: 多维度文本统计
4. **多模式交互**: 支持 GUI、TUI、命令行测试
5. **扩展能力**: 可集成多种 MCP 工具
