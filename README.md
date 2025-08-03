RecipeTracker
A private, lightweight recipe manager built with Kotlin and Jetpack Compose.
Quickly add recipes, mark favorites, and filter to surface what matters—designed for home cooks who want a personal, uncluttered way to keep track of their own cooking.

Features (Implemented)
Add new recipes with a title.

Mark/unmark recipes as favorites.

Filter to show only favorite recipes.

Responsive UI using Jetpack Compose.

State management via ViewModel + Kotlin Flow.

Modular architecture (MVVM) with clean separation between UI and data logic.

Temporary in-memory storage implementation to get core flows working reliably without blocking on persistence setup.

Planned / Future Enhancements
Persistent local storage using Room (currently the app uses an in-memory repository).

Recipe tagging/categories (e.g., vegan, gluten-free).

Attach images to recipes.

Edit/delete existing recipes.

History of cooked recipes ("made it" tracking).

Background syncing or backup (e.g., WorkManager).

Runtime permissions for media access if adding photos.

Tech Stack
Kotlin

Jetpack Compose for declarative UI

MVVM architecture

ViewModel and Kotlin Flow for state handling

In-memory repository (current) with planned migration to Room for persistence

Android Studio (Gradle/Kotlin DSL)

Project Structure (key parts)
MainActivity.kt – Entry point, hosts the composable app UI.

InMemoryRecipeViewModel.kt – ViewModel encapsulating recipe logic and filtering.

InMemoryRecipeViewModelFactory.kt – Factory for creating the ViewModel with the repository.

InMemoryRecipeRepository.kt – Temporary data layer in memory.

data.local.RecipeEntity.kt – Recipe data model.

(Future) RecipeRepository, AppDatabase, and Room entities/DAOs for persistence.

Setup & Run Instructions
Prerequisites
Android Studio (Electric Eel or later recommended)

JDK 17+

Android SDK with API level 24+

Steps
Clone the repository:
git clone <your-repo-url>
cd RecipeTracker

Open the project in Android Studio.

Let Gradle sync.

Run the app on an emulator or connected device (API 24+).

Tap the + button to add a recipe, favorite it with the heart icon, and filter favorites with the toggle.

Switching to Room (Persistence)
The current implementation uses an in-memory repository for quick iteration. To migrate to persistent storage:

Implement the AppDatabase with Room and RecipeDao.

Replace InMemoryRecipeRepository with RecipeRepository that uses the DAO.

Use RecipeViewModel and its corresponding RecipeViewModelFactory instead of the in-memory versions.

Ensure annotation processing (kapt) is correctly configured so Room generates the required implementation classes.

Testing
(Optional) Add unit tests for ViewModel logic and UI tests using Compose’s testing APIs to validate flows like adding, favoriting, and filtering.

Usage Example
Add a recipe: Tap +, enter “Tomato Soup”, press Save.

Favorite: Tap the heart icon on a recipe card.

Filter: Tap the filter icon to toggle showing only favorites.

Git & Development Notes
Meaningful commits show progress (e.g., add in-memory MVVM implementation, add favorite filter, prepare self-reflection draft).

The architecture isolates the data layer so swapping from in-memory to Room requires minimal UI changes.

Self-Reflection & Promotional Materials
A 500-word self-reflection using Gibbs’ Reflective Cycle is included in the submission.

A 3–5 minute promotional video demonstrates the core app flows and future roadmap.
