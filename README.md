# 🌍 AI Trip Planner — Agentic Travel Planning Application

An intelligent, AI-powered travel planning assistant that creates comprehensive, personalized trip itineraries for destinations worldwide. Powered by Large Language Models (LLMs) and integrated with real-time data sources to deliver detailed travel plans, cost breakdowns, and recommendations.

---

## 🎯 Problem Statement

Planning a trip is often a time-consuming and overwhelming task. Travelers typically spend **hours researching across multiple websites and platforms** to gather essential information such as:

- 🏨 Finding suitable accommodations within budget
- 🍽️ Identifying good restaurants and local cuisines
- 🎡 Discovering popular attractions and hidden gems
- 🚗 Understanding local transportation options
- 💰 Estimating total trip costs and daily budgets
- ☁️ Checking weather conditions and the best time to visit
- 📅 Creating a day-by-day itinerary that balances activities

### Key Challenges Faced by Travelers:

1. **Information Overload** — Scattered data across countless travel blogs, review sites, and booking platforms makes it hard to compile a unified plan.
2. **Time-Consuming Research** — Manually researching every detail (hotels, food, transport, costs) can take days.
3. **Lack of Personalization** — Generic travel guides don't account for individual preferences or budgets.
4. **Missing Off-Beat Experiences** — Most travelers only see mainstream tourist spots and miss out on unique local experiences.
5. **Budget Uncertainty** — Without proper cost breakdowns, travelers often overspend or run short on funds.
6. **Currency & Weather Confusion** — International travelers struggle with currency conversions and weather planning.

### 💡 Our Solution

The **AI Trip Planner** solves these problems by acting as an **intelligent travel companion** that:

- ✅ Consolidates all travel information in **one place**
- ✅ Generates **complete itineraries in seconds** instead of hours
- ✅ Provides **two distinct plans** — popular tourist spots AND off-beat hidden gems
- ✅ Delivers **detailed cost breakdowns** and per-day budget estimates
- ✅ Integrates **real-time data** (weather, prices, availability) via external APIs
- ✅ Uses **agentic AI** to make smart decisions and recommendations
- ✅ Presents everything through a **simple, conversational interface**

By leveraging Large Language Models combined with specialized tools (Places API, Weather API, etc.), this application transforms hours of manual research into a single, comprehensive travel plan delivered in seconds.

---

## 📖 Overview

The **AI Trip Planner** is an agentic application that leverages the power of Large Language Models combined with various external tools and APIs to generate comprehensive travel plans. Users simply enter a destination, and the system returns detailed itineraries covering accommodations, attractions, restaurants, activities, transportation, weather, and complete cost breakdowns.

The application offers two distinct itinerary types for every destination:
- **Popular Tourist Itinerary** — covering famous landmarks and well-known attractions
- **Off-Beat Itinerary** — showcasing hidden gems and lesser-known local spots

---

## ✨ Features

- 🗺️ **Dual Itinerary Generation** — Tourist hotspots + off-beat locations for the same destination
- 🏨 **Smart Hotel Recommendations** — Curated accommodations with approximate nightly rates
- 🍽️ **Restaurant Suggestions** — Local dining recommendations with average meal costs
- 🎡 **Activity Planning** — Detailed list of activities and experiences
- 🚗 **Transportation Guidance** — Local transport options with relevant details
- 💰 **Cost Breakdown** — Itemized expense planning and daily budget estimates
- ☁️ **Real-time Weather Info** — Current conditions and forecasts for the destination
- 📅 **Day-by-Day Itinerary** — Complete schedule planning
- 💬 **Interactive Chat Interface** — User-friendly Streamlit frontend
- ⚡ **FastAPI Backend** — High-performance API for handling requests

---

## 🛠️ Tech Stack

| Category | Technologies |
|----------|-------------|
| **Language** | Python 3.10 |
| **Backend Framework** | FastAPI, Uvicorn |
| **Frontend Framework** | Streamlit |
| **AI/ML Framework** | LangChain, LangGraph |
| **Package Manager** | uv |
| **APIs** | Google Places API, OpenWeather API, Foursquare API |
| **Environment Management** | python-dotenv |
| **Version Control** | Git, GitHub |

---

## 🏗️ Architecture

```
┌──────────────────┐         ┌──────────────────┐         ┌──────────────────┐
│                  │         │                  │         │                  │
│   Streamlit UI   │────────▶│   FastAPI        │────────▶│   LangChain      │
│   (Frontend)     │◀────────│   Backend        │◀────────│   AI Agent       │
│                  │         │                  │         │                  │
└──────────────────┘         └──────────────────┘         └─────────┬────────┘
                                                                     │
                                                                     ▼
                                              ┌──────────────────────────────────────┐
                                              │         External Tools / APIs        │
                                              │  ┌──────────┐  ┌──────────┐         │
                                              │  │ Places   │  │ Weather  │  ...    │
                                              │  └──────────┘  └──────────┘         │
                                              └──────────────────────────────────────┘
```

---

## 📁 Project Structure

```
AI_Trip_Planner/
│
├── streamlit_app.py           # Streamlit frontend application
├── main.py                    # FastAPI backend entry point
├── setup.py                   # Package setup configuration
├── pyproject.toml             # Project metadata and dependencies
├── requirements.txt           # Python dependencies
├── .env                       # Environment variables (not committed)
├── .gitignore                 # Git ignore rules
├── README.md                  # Project documentation
│
├── agents/                    # AI agent definitions
│   └── travel_agent.py
│
├── tools/                     # External tool integrations
│   ├── place_tool.py
│   ├── weather_tool.py
│   └── currency_tool.py
│
├── prompts/                   # System prompts and templates
│   └── system_prompt.py
│
├── config/                    # Configuration files
│   └── settings.py
│
└── utils/                     # Helper functions
    └── helpers.py
```

---

## 📋 Prerequisites

Before running this project, ensure the following are installed:

- **Python 3.10** or higher
- **uv** (Python package manager) — [Installation guide](https://docs.astral.sh/uv/)
- **Git** — for cloning the repository
- **API Keys** (see Configuration section)

---

## 🚀 Installation

### Step 1: Clone the repository

```bash
git clone https://github.com/Aryan09092001/AI_Trip_Planner.git
cd AI_Trip_Planner
```

### Step 2: Create a virtual environment with uv

```bash
uv venv --python 3.10
```

### Step 3: Activate the virtual environment

**On Windows:**
```bash
.venv\Scripts\activate
```

**On macOS/Linux:**
```bash
source .venv/bin/activate
```

### Step 4: Install dependencies

```bash
uv pip install -r requirements.txt
```

---

## ⚙️ Configuration

### Step 1: Create a `.env` file in the project root

```bash
notepad .env
```

### Step 2: Add the following environment variables

```env
# LLM API Keys
GROQ_API_KEY=your_groq_api_key_here
OPENAI_API_KEY=your_openai_api_key_here

# Tool API Keys
GOOGLE_API_KEY=your_google_places_api_key_here
OPENWEATHERMAP_API_KEY=your_openweather_api_key_here
TAVILY_API_KEY=your_tavily_api_key_here
FOURSQUARE_API_KEY=your_foursquare_api_key_here

# Application Settings
BACKEND_URL=http://localhost:8000
```

### Where to get the API keys:

| API | Free Tier | Sign-up Link |
|-----|-----------|--------------|
| **Groq** | ✅ Free | [console.groq.com](https://console.groq.com) |
| **OpenAI** | 💰 Paid | [platform.openai.com](https://platform.openai.com) |
| **Google Places** | ✅ $300 free credit | [console.cloud.google.com](https://console.cloud.google.com) |
| **OpenWeather** | ✅ Free | [openweathermap.org](https://openweathermap.org/api) |
| **Tavily** | ✅ Free | [tavily.com](https://tavily.com) |
| **Foursquare** | ✅ Free | [foursquare.com/developers](https://foursquare.com/developers/) |

---

## 💻 Usage

### Running the application requires TWO terminals

### Terminal 1 — Start the Backend (FastAPI)

```bash
# Activate the environment
.venv\Scripts\activate

# Run the FastAPI server
uvicorn main:app --reload --port 8000
```

The backend will be available at: **http://localhost:8000**

### Terminal 2 — Start the Frontend (Streamlit)

```bash
# Activate the environment
.venv\Scripts\activate

# Run the Streamlit app
streamlit run streamlit_app.py
```

The frontend will open automatically at: **http://localhost:8501**

### Using the App

1. Open the Streamlit interface in the browser
2. Enter a travel query, for example:
   - *"Plan a trip to Goa for 5 days"*
   - *"Create an itinerary for Paris in winter"*
   - *"Suggest a weekend trip to Mumbai"*
3. Click **Send** and wait for the AI to generate the trip plan
4. The complete itinerary will be displayed with all relevant details



---

## 🔮 Future Enhancements

- [ ] User authentication and saved itineraries
- [ ] PDF export of travel plans
- [ ] Multi-language support
- [ ] Integration with booking platforms (hotels, flights)
- [ ] Currency conversion in real-time
- [ ] Interactive map visualization
- [ ] Voice input support
- [ ] Mobile-responsive design
- [ ] Trip sharing via social media
- [ ] Personalized recommendations based on user preferences

---

⭐ **If this project helped you, please consider giving it a star on GitHub!**
