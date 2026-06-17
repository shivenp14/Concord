# Concord

## Project Goal

Concord is an explainable group movie-decision engine that helps people decide what to watch by balancing individual preferences, group compromise, mood, viewing context, runtime constraints, and streaming availability.

The goal is not just to recommend movies. Concord is designed to reduce movie choice paralysis, especially for groups that struggle to agree on one option. It recommends movies that work well for the group as a whole and explains why each suggestion makes sense.

---

## Overview of Flow

```text
Create watch session
→ collect each user’s preferences
→ build individual preference profiles
→ represent users and movies in a knowledge graph
→ generate candidate movies with graph-based methods
→ rank movies for group compromise
→ show recommendations with explanations
→ collect feedback after the decision
```

### 1. Create a Watch Session

Users start a session based on the viewing situation, such as solo watching, a couple, roommates, friends, or family night.

### 2. Collect Preferences

Each user completes a quick onboarding process by rating movies, selecting liked and disliked genres, choosing moods, and adding constraints such as runtime, platform, rating, release year, or content restrictions.

### 3. Build Preference Profiles

Concord creates a separate profile for each user instead of merging the group into one generic profile. Each profile can include liked movies, disliked movies, preferred genres, avoided genres, moods, themes, and platform access.

### 4. Construct the Knowledge Graph

The system represents users, movies, genres, moods, themes, actors, directors, ratings, and streaming platforms as connected nodes in a graph. This allows Concord to reason through relationships such as:

```text
User → liked movie → shared genre → recommended movie
```

### 5. Generate and Rank Recommendations

The graph engine generates candidate movies using methods such as Personalized PageRank, graph traversal, or Node2Vec-style embeddings. The group ranking engine then scores movies based on shared fit, individual match strength, hard constraints, and strong-dislike penalties.

### 6. Explain the Result

Each recommendation includes a clear explanation showing why the movie fits the group, which users it matches, what tradeoffs were made, and why certain movies were excluded.

---

## Current Progress

---

## Future Plans

- Build the initial movie knowledge graph using MovieLens data and movie metadata.
- Implement basic onboarding for collecting user preferences.
- Create individual user preference profiles.
- Develop the first version of candidate generation using Personalized PageRank.
- Add constraint filtering for runtime, platform, rating, and content preferences.
- Implement group ranking logic that balances shared fit and individual dislikes.
- Generate simple explanation paths for each recommendation.
- Build a lightweight interface for creating sessions and viewing recommendations.
- Add feedback collection to evaluate whether Concord helps groups decide faster and with less disagreement.
- Compare Concord against simple baselines such as popularity ranking, average score ranking, and collaborative filtering.
