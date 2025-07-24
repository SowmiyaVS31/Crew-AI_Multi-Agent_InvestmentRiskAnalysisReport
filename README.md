# 📊 Investment Risk Analysis with CrewAI Multi-Agent System

<div align="center">

![Python](https://img.shields.io/badge/python-v3.8+-blue.svg)
![CrewAI](https://img.shields.io/badge/CrewAI-Multi--Agent-green.svg)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

*Intelligent multi-agent AI workflow for investment risk analysis and trading strategy development*

</div>

---

## 🎯 Overview

This Jupyter notebook demonstrates a sophisticated multi-agent AI workflow for investment risk analysis and trading strategy development using the CrewAI framework. It employs multiple specialized AI agents, each with distinct roles, to collaboratively analyze market data, develop trading strategies, plan trade execution, and assess risks. The workflow is orchestrated by a Manager LLM, enabling dynamic, modular, and autonomous decision-making.

---

## ✨ Key Features

###  **Multi-Agent Collaboration**
Four specialized agents (Data Analyst, Trading Strategy Developer, Trade Advisor, Risk Advisor) work together, each focusing on a specific aspect of the investment process.

###  **Real-Time Data & Web Tools**
Agents use tools for web scraping and real-time search to gather up-to-date market information.

###  **Orchestrated by Manager LLM**
A large language model (e.g., GPT-3.5-turbo) manages the workflow, routing tasks and data between agents.

###  **Customizable Inputs**
User can specify stock ticker, initial capital, risk tolerance, and trading preferences.

###  **Extensible & Modular**
Easily add new agents, tools, or tasks for more complex workflows.

---

## 🔄 Workflow

### 1.  **Setup & Installation**
- Installs required packages: `crewai`, `crewai_tools`, `langchain_community`
- Loads API keys from environment/user data

### 2.  **Agent Definitions**
- **📈 Data Analyst:** Monitors and analyzes market data, identifies trends
- **💡 Trading Strategy Developer:** Designs and refines trading strategies
- **📋 Trade Advisor:** Plans optimal trade execution
- **⚠️ Risk Advisor:** Assesses risks and recommends mitigation

### 3.  **Task Definitions**
Each agent is assigned a specific task:
- Analyze market data for a selected stock
- Develop strategies based on analysis and user risk tolerance
- Plan trade execution considering market conditions
- Evaluate risks and suggest safeguards

### 4.  **Crew & Manager LLM**
- All agents and tasks are grouped into a `Crew`
- The Manager LLM orchestrates the workflow in hierarchical mode, passing outputs between agents as needed

### 5. ▶ **Execution**
- User provides input parameters (stock, capital, risk tolerance, etc.)
- The crew is kicked off, and agents collaborate to produce a comprehensive investment and risk analysis report

### 6.  **Output**
- Results are displayed in Markdown, including insights, strategies, execution plans, and risk assessments

---

## 💻 Example Usage

```python
financial_trading_inputs = {
    'stock_selection': 'NVDA',
    'initial_capital': '100000',
    'risk_tolerance': 'Medium',
    'trading_strategy_preference': 'Day Trading',
    'news_impact_consideration': True
}
result = financial_trading_crew.kickoff(inputs=financial_trading_inputs)
from IPython.display import Markdown
Markdown(result)
```

---

## 📋 Sample Output

```markdown
Risk Analysis Report for Proposed Trading Strategies for AAPL:

Introduction:
The following risk analysis report aims to evaluate the potential risks associated with the proposed trading strategies for AAPL and provide recommendations for risk mitigation strategies. The strategies include Long-Term Investment Strategy, Options Trading Strategy, Swing Trading Strategy, and Diversification Strategy. Each strategy presents unique risks that should be carefully considered to optimize returns while managing risk effectively.

Long-Term Investment Strategy:
Risk Factors:
- Market volatility
- Potential for capital loss over time
Recommendations for Risk Mitigation:
- Set clear investment goals
- Understand risk tolerance
- Regularly review investment portfolio

Options Trading Strategy:
Risk Factors:
- Complexity of the strategy
- Leverage
- Time decay
- Volatility
- Counterparty risk
- Early assignment
- Liquidity
Recommendations for Risk Mitigation:
- Gain thorough understanding of options trading
- Use options to hedge positions
- Be prepared for large price swings

Swing Trading Strategy:
Risk Factors:
- Frequency of trading
- Market volatility
- Emotional decision making
Recommendations for Risk Mitigation:
- Incorporate risk management
- Set specific conditions like stop loss
- Avoid overstaying positions

Diversification Strategy:
Risk Factors:
- Spreading resources too thin
- Losing focus on core business
- Lack of understanding in new markets
Recommendations for Risk Mitigation:
- Carefully allocate resources
- Maintain focus on core business
- Gain understanding of new markets

Conclusion:
While the proposed trading strategies for AAPL present various risks, implementing the recommended risk mitigation strategies can help optimize returns and manage risk effectively. By aligning execution methods with the user's risk tolerance and investment goals, informed decisions can be made to maximize profitability. It is crucial to continuously monitor and adjust strategies based on market conditions and individual preferences to achieve long-term success in trading activities.
```

---

## 🛠️ Technical Details

### 🤖 Agents & Tools
- **Agents:** Defined using CrewAI's `Agent` class, each with a role, goal, backstory, and toolset
- **Tools:**
  - `SerperDevTool`: For real-time web search (requires SERPER API key)
  - `ScrapeWebsiteTool`: For extracting data from financial news and stock sites
- **Manager LLM:** Uses OpenAI's GPT-3.5-turbo (or similar) to coordinate the workflow

### 🎯 Task Orchestration
- **Process Mode:** `Process.hierarchical` allows the Manager LLM to dynamically route outputs between agents and decide task order
- **Inputs:**
  - `stock_selection`: e.g., 'AAPL', 'NVDA'
  - `initial_capital`: e.g., '100000'
  - `risk_tolerance`: 'Low', 'Medium', 'High'
  - `trading_strategy_preference`: e.g., 'Day Trading', 'Swing Trading'
  - `news_impact_consideration`: Boolean

### 📋 Requirements
-  Python 3.8+
-  Jupyter Notebook or Google Colab
-  Packages: `crewai`, `crewai_tools`, `langchain_community`, `openai`, `serper`
-  API Keys:  
  - `OPENAI_API_KEY` (for LLM)  
  - `SERPER_API_KEY` (for web search)

### 🚀 How to Run
1. Install dependencies (first cell of the notebook)
2. Set your API keys (either in Colab `userdata` or as environment variables)
3. Run all cells in order
4. Review the Markdown output for the full analysis

---

## 🎨 Customization
- Add or modify agents for new roles (e.g., Compliance, Portfolio Optimization)
- Change the LLM model or temperature for different creativity/rigor
- Integrate additional data sources or tools as needed

---

## 📚 References
- [CrewAI Documentation](https://docs.crewai.com/)
- [LangChain Community](https://python.langchain.com/)
- [OpenAI API](https://platform.openai.com/docs/)
- [Serper API](https://serper.dev/)

---

## 📄 License

[MIT License] or specify your own.

---

<div align="center">

*Happy Trading! 📈*

</div>
