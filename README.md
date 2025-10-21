# The Immortal Alchemist of Stardew Valley — Story-Driven MOD Design Document

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Stardew Valley](https://img.shields.io/badge/Stardew%20Valley-1.6+-green.svg)](https://www.stardewvalley.net/)
[![SMAPI](https://img.shields.io/badge/SMAPI-3.18+-orange.svg)](https://smapi.io/)

## 📖 Overview

**The Immortal Alchemist of Stardew Valley** is an innovative hybrid narrative mod that seamlessly blends farming simulation with cultivation fantasy and AI-powered story generation. This mod transforms your gameplay into a personalized, evolving novel where every action contributes to an ongoing literary adventure.

### 🎯 Key Features
- **AI-Powered Story Generation**: Each in-game day generates a new chapter in your personal novel
- **Cultivation System**: Progress through traditional Chinese cultivation stages (Mortal → Ascended)
- **Dynamic NPC Interactions**: Master Xian reacts to your choices and influences the narrative
- **Alchemy Crafting**: Create mystical elixirs with narrative significance
- **Personalized Storytelling**: Your gameplay style shapes the tone and direction of the story

### 📚 Original Novel
This mod is directly adapted from the web novel:  
**[The Immortal Alchemist of Stardew Valley](https://www.royalroad.com/fiction/136670/trapped-in-the-character-library)** by DRAMA FM

---

## 🎮 Core Concept

**Type:** Hybrid Narrative Mod (Farming + Cultivation + AI Story Writing)  
**Author:** DRAMA FM  
**Core Mechanic:**  
> This mod is **directly adapted from the novel**, and at the same time, it **writes new novel chapters based on player actions each in-game day**.

As the player interacts with the mod — farming, crafting, meditating, or talking to NPCs — the system records these activities and uses an AI narrative generator to create new story chapters. Each day of gameplay becomes a new entry in the evolving novel "The Immortal Alchemist of Stardew Valley".

---

## 🔄 Narrative–Gameplay Integration

### 2.1 Dual Loop System
| Layer | Function |
|-------|----------|
| **Game Layer (Simulation)** | Players live in Stardew Valley, meeting Master Xian, cultivating Qi, crafting elixirs, and exploring hidden realms. |
| **Narrative Layer (AI Novel Writer)** | The mod exports daily logs of interactions and choices. An AI agent transforms them into a formatted novel chapter (Markdown). |

### 2.2 Chapter Generation Flow
1. **Daily Activities**: Player completes farming, crafting, and social interactions
2. **Data Collection**: Mod tracks location, dialogues, energy gains, and relationships
3. **Log Creation**: At day's end, a structured "Daily Log" file is generated
4. **AI Processing**: External AI Story Engine reads and processes the log
5. **Chapter Generation**: New novel chapter (e.g., `CHAPTER_021.md`) is created and added to the ongoing story

This system turns every player's journey into a unique serialized novel — blending interactive fiction with simulation gameplay.

---

## ⚔️ Core Gameplay Systems

### 3.1 Cultivation & Energy System
- **Mechanic**: Gather Spirit Energy (SE) through meditation, farming, or alchemy
- **Purpose**: SE affects both in-game abilities *and* the "narrative depth" of generated chapters
- **Progression Stages**: Mortal → Qi Gatherer → Foundation → Core Formation → Nascent Soul → Ascended

Each breakthrough expands story possibilities, unlocking higher-dimensional narrative arcs and new gameplay mechanics.

### 3.2 Alchemy & Crafting System
- **Workbench**: Alchemy Cauldron
- **Function**: Combine herbs, ores, and crops to create mystical elixirs
- **Narrative Impact**: Each potion crafted has specific narrative meaning and triggers unique story events

**Example Potions:**
| Item | Effect | Narrative Trigger |
|------|--------|-------------------|
| Spirit Elixir | +Energy Regen | "Refined Qi" chapter |
| Starfire Dew | Crop boost | "Stardew Miracle" event |
| Soulstone Pill | Permanent stat gain | "Ascension Dream" chapter |

### 3.3 NPC: Master Xian
**Role**: The Immortal Alchemist — mentor, observer, and meta-commentator  
**Behavior**: Tracks player morality, curiosity, and cultivation progress  
**Narrative Function**:
- Reacts to your choices (wise, sarcastic, or cryptic)
- Dialogue snippets become direct narrative quotes in AI-written chapters
- Provides guidance and unlocks new cultivation techniques

**Friendship Rewards:**
| Hearts | Reward | Narrative Effect |
|:------:|--------|------------------|
| 2 | Spirit Crop seeds | "The First Lesson" |
| 4 | Alchemy recipes | "The Cauldron Awakens" |
| 6 | Spirit portal access | "The Gate Opens" |
| 8 | Ascension dream | "Beyond Stardew Valley" |
| 10 | Co-authoring the novel ending | "Immortal Chronicle" |

---

## 🤖 AI Novel Generation System

### 4.1 Daily Story Data Collection
At the end of each in-game day, the mod exports structured data:

```json
{
  "day": 14,
  "location": "Mountain Lake",
  "npc_interactions": ["Master Xian", "Leah"],
  "energy_collected": 56,
  "alchemy_recipes_used": ["Heavenly Dew"],
  "weather": "Rain",
  "player_thoughts": "I feel the valley watching me.",
  "cultivation_stage": "Qi Gatherer",
  "morality_alignment": "Neutral",
  "discoveries_made": ["Ancient Ruins", "Spirit Herb Garden"]
}
```

### 4.2 Narrative Personalization
- **Style Adaptation**: Matches player's gameplay style (poetic, pragmatic, or mysterious)
- **Character Development**: Reflects player choices and relationship progression
- **Plot Twists**: Based on game events and emergent narrative elements
- **Thematic Consistency**: Maintains cultivation fantasy tone throughout

---

## 🛠️ Technical Implementation

### 5.1 MOD Architecture
- **Framework**: SMAPI (Stardew Modding API)
- **Data Collection**: Real-time event tracking and logging
- **File Management**: Structured JSON logs and Markdown chapter generation
- **AI Integration**: REST API communication with external AI services

### 5.2 File Structure
```
Immortal-Alchemist-MOD/
├── Content/
│   ├── Characters/     # NPC data and dialogue trees
│   ├── Items/          # Custom items and alchemy recipes
│   └── Maps/           # New map areas and spirit realms
├── Data/
│   ├── DailyLogs/      # JSON log files
│   └── StoryChapters/  # Generated Markdown chapters
└── Scripts/
    ├── EventHandlers/  # Game event processing
    └── AIInterface/    # AI communication layer
```

### 5.3 Compatibility & Requirements
- **Platforms**: Windows, macOS, Linux
- **Stardew Valley**: Version 1.6+
- **Dependencies**: SMAPI 3.18+, .NET 6.0+
- **AI Services**: OpenAI GPT, Claude, or compatible models

---

## 🚀 Installation & Setup

### Quick Start
1. Install [SMAPI](https://smapi.io/) for your platform
2. Download the latest release from the [Releases page]
3. Extract to your Stardew Valley Mods folder
4. Launch the game through SMAPI
5. Configure AI service credentials in `config.json`

### Configuration
Edit `config.json` to set up your preferred AI service:
```json
{
  "ai_service": "openai",
  "api_key": "your-api-key-here",
  "model": "gpt-4",
  "writing_style": "cultivation_fantasy",
  "chapter_length": "medium"
}
```

---

## 📊 Development Roadmap

### Phase 1: Core Systems ✅
- [x] Basic MOD framework and SMAPI integration
- [x] Master Xian NPC implementation
- [x] Spirit Energy cultivation system
- [x] Basic alchemy crafting

### Phase 2: Narrative Integration 🚧
- [ ] Daily log generation system
- [ ] AI story generation interface
- [ ] Chapter management and organization
- [ ] Player choice tracking and narrative branching

### Phase 3: Advanced Features 📅
- [ ] Multiple ending system
- [ ] Player-authored content tools
- [ ] Community story sharing platform
- [ ] Visual narrative editor

---

## 🤝 Contributing

We welcome contributions from the community! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

### Areas for Contribution
- **Localization**: Help translate the mod into other languages
- **Testing**: Report bugs and provide gameplay feedback
- **Content**: Suggest new alchemy recipes or cultivation techniques
- **Code**: Improve the AI integration or add new features

### Code Standards
- Follow C# best practices and SMAPI coding conventions
- Include comprehensive XML documentation
- Write unit tests for new functionality
- Ensure backward compatibility with Stardew Valley 1.6+

---

## 📄 License & Acknowledgments

### License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

### Acknowledgments
- **ConcernedApe**: For creating the wonderful world of Stardew Valley
- **SMAPI Community**: For providing an excellent modding framework
- **AI Model Providers**: For enabling innovative narrative generation
- **Beta Testers**: For valuable feedback and improvement suggestions

---

## 📞 Support & Contact

- **GitHub Issues**: [Report bugs or request features]
- **Discord**: [Join our community server]
- **Email**: drama.fm@example.com
- **Documentation**: [Full documentation and API reference]

---

*Transform your Stardew Valley journey into an immortal legend — where every day writes a new chapter in your personal cultivation saga.* 🌟

