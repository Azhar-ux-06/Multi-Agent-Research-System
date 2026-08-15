# Multi-Agent AI Research System

Give it a topic, and it does the research for you. This project automates what a small research team would normally do by hand: search the web, read through the most useful source, write it up properly, and then review the write-up before calling it done.

Instead of throwing everything at one AI and hoping for a decent answer, the work is split across a few specialized agents that each handle one part of the job, and pass their output to the next one.

## How it works

1. **Search Agent** - takes the topic and searches the web for recent, reliable sources
2. **Reader Agent** - picks the most relevant result out of those and scrapes the actual page for deeper content
3. **Writer** - takes the search results plus the scraped content and drafts a proper report: intro, key findings, conclusion, sources
4. **Critic** - reads the report back and reviews it, scoring it out of 10 and pointing out what's strong and what's missing

By the time you see the final output, it's already been through a review pass.

## Tech Stack

- Python
- LangChain - for the agents and chains
- OpenAI (gpt-4o-mini) - the model behind every agent
- Tavily - web search
- BeautifulSoup - scraping and cleaning up page content
- Streamlit - the browser UI

## Project Structure

```
Multi-Agent-Research-System/
├── tools.py         # Web search and page scraping tools the agents use
├── agents.py        # The agents and chains - search, reader, writer, critic
├── pipeline.py       # Runs the full pipeline end to end, works from the terminal
├── app.py            # Streamlit UI for running it in the browser
└── requirements.txt
```

## Setup

1. Clone the repo
   ```
   git clone https://github.com/Azhar-ux-06/Multi-Agent-Research-System.git
   cd Multi-Agent-Research-System
   ```

2. Install dependencies
   ```
   pip install -r requirements.txt
   ```

3. This project runs on API integrations. Create a `.env` file in the project root:
   ```
   OPENAI_API_KEY=
   TAVILY_API_KEY=
   ```

4. Run it from the terminal
   ```
   python pipeline.py
   ```
   or launch the web version
   ```
   streamlit run app.py
   ```

## Usage

Type in a topic and the system takes it from there, searching, reading, writing, and reviewing on its own. In the Streamlit version you can watch each step happen live, and download the final report once it's done.

## Future Improvements

- Pull from more than one source instead of just the top result
- Add a PDF export alongside the markdown download
- Add retry logic for when a search or scrape fails
- Read the final report out loud (text-to-speech)

## Author

Built by Azhar Sheikh
[LinkedIn](https://linkedin.com/in/azhar-sheikh-a5a0bb2b5) - [GitHub](https://github.com/Azhar-ux-06)