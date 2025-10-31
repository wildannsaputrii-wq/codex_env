### **Product Requirements Document: Crypto Quant AI Agent**

**1. Introduction & Vision**

*   **Product:** Crypto Quant AI Agent
*   **Vision:** To create an automated AI agent that provides actionable, data-driven cryptocurrency trading recommendations to help users make profitable trades. The agent will analyze multiple data sources, including real-time market data and news sentiment, to generate comprehensive short-term and long-term trading strategies for both spot and leveraged trading.

**2. Problem Statement**

*   **The Problem:** Cryptocurrency traders, from novice to experienced, face the challenge of processing vast amounts of complex information to make timely and profitable trading decisions. This includes analyzing technical chart data across multiple timeframes, staying updated on market news, and understanding market sentiment, all of which is time-consuming and requires significant expertise.
*   **How We Solve It:** The Crypto Quant AI Agent automates this entire process. It ingests live market data and recent news articles, performs a multi-faceted analysis, and delivers clear, structured trading recommendations directly to the user via a messaging platform like Telegram. This saves the user time, reduces the complexity of market analysis, and provides a data-backed foundation for their trading decisions.

**3. User Personas**

*   **Retail Crypto Trader:** Individuals who actively trade cryptocurrencies and are looking for an edge in the market. They need quick, reliable insights to supplement their own research and capitalize on trading opportunities.
*   **Crypto Enthusiast/Hobbyist:** Users who are interested in the crypto market but may not have the time or deep technical knowledge to perform detailed analyses. They are looking for a simplified way to participate in trading with informed guidance.

**4. Key Features & Functionality**

**4.1. User Interaction & Input**
*   **Trigger:** The workflow is initiated when a user sends a message with a cryptocurrency ticker symbol (e.g., "ETH," "BTC") via a Telegram trigger.
*   **Input Processing:** The system shall take the user's input, format it to be compatible with data APIs (e.g., convert "eth" to "ETHUSDT"), and use it to fetch relevant data.

**4.2. Data Aggregation**
*   **Live Market Data:** The agent must fetch live candlestick data from a reliable source (e.g., Binance API) for the specified cryptocurrency.
    *   It will gather data across multiple timeframes: 15-minute, 1-hour, and 1-day candles.
*   **News Article Aggregation:** The agent will fetch relevant crypto news articles from the past three days from a news API.

**4.3. Data Analysis Engine**
The core of the agent is a three-pronged analysis approach:
*   **Primary Signal Analysis (Price Action):**
    *   Analysis based on direct price action from candlestick data.
    *   Identifies key support and resistance levels, trendlines, and chart patterns.
*   **Lagging Indicator Analysis:**
    *   Calculates and interprets standard technical indicators such as MACD (Moving Average Convergence Divergence), RSI (Relative Strength Index), and OBV (On-Balance Volume).
    *   This provides confirmation and additional context to the primary price action signals.
*   **Sentiment Analysis:**
    *   Analyzes the aggregated news articles to determine the overall market sentiment.
    *   Categorizes sentiment for both short-term and long-term outlooks as "Positive," "Negative," or "Neutral."

**4.4. Recommendation Generation & Output**
*   **AI Agent Processing:** An AI model (e.g., Google Gemini) will receive all the processed technical data and sentiment analysis. It will synthesize this information to generate detailed trading recommendations.
*   **Output Content:** The final output delivered to the user must be a structured message containing:
    *   **Spot Trading Recommendations:**
        *   Broken down into **Short-term** and **Long-term** strategies.
        *   Each section must include:
            *   **Action:** Buy, Sell, or Hold.
            *   **Entry Price:** Suggested price range for entry.
            *   **Stop-Loss Level:** A price at which to sell to limit losses.
            *   **Take Profit Level:** Price targets for selling to secure profits.
            *   **Rationale:** A detailed explanation for the recommendation, broken down into Primary Signals, Lagging Indicators, and Sentiment Analysis.
    *   **Leveraged Trading Recommendations:**
        *   Also broken down into **Short-term** and **Long-term**.
        *   Each section must include:
            *   **Position:** Long or Short.
            *   **Recommended Leverage:** (e.g., 3x, 5x).
            *   **Entry, Stop-Loss, and Take Profit** levels.
            *   **Detailed Rationale** similar to the spot recommendations.

**4.5. Delivery**
*   **Platform:** The recommendations will be sent as messages on Telegram.
*   **Formatting:** The message must be formatted for readability, using HTML parsing for bolding, line breaks, and clear section headers. The system must handle message length limitations by splitting the content into multiple messages if necessary.

**5. Technical Considerations**

*   **Platform:** The workflow is built on a no-code/low-code automation platform (n8n is shown in the video).
*   **APIs:**
    *   Messaging: Telegram API
    *   Market Data: Binance API (or a similar crypto exchange API)
    *   News: A dedicated News API
*   **AI Model:** A powerful language model capable of processing large contexts and structured data, such as Google Gemini or OpenAI's GPT models.

**6. Success Metrics**

*   **User Engagement:** Number of daily active users and requests.
*   **Accuracy of Recommendations:** (To be tracked hypothetically) Percentage of profitable trade recommendations.
*   **User Satisfaction:** Qualitative feedback from users on the clarity, timeliness, and usefulness of the recommendations.