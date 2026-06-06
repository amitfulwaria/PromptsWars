# AI Cooking Meal Planner (CulinaryAI)

A premium, interactive, and visually stunning single-page web application that helps users generate custom daily meal plans, consolidated grocery lists, and budget analyses. The app will support both a fully-featured, dynamically simulated mock mode and a real Gemini AI integration using client-side API calls with secure local storage key management.

## Proposed Design & Aesthetic Enhancements

We will replace the basic styling with a top-tier modern interface:
- **Obsidian & Dark Forest Green Color Palette**: Deep rich forest gradients (`#08120a` to `#112415`), sleek glassmorphic container cards (`backdrop-filter: blur(16px)` with thin emerald borders), and vibrant emerald-green (`#10b981`) and gold accents.
- **Tailwind + Custom CSS Animations**: Smooth animations for page transitions, tab switching, and card hover effects.
- **Dynamic Culinary Loading Screen**: An immersive loading sequence displaying rotating animated status messages (e.g., *"Chop-chop! Prep work in progress... 🥬"*, *"Simmering the sauces... 🍲"*, *"Plating your customized meals... 🍽️"*) to keep the user engaged.
- **Google Typography**: Using the premium geometric sans-serif **Outfit** font from Google Fonts for a modern, high-end look.

## Core Features to Implement

1. **AI API Key Settings (Settings Panel)**:
   - A gear icon in the header opening a modal that allows users to enter their Google Gemini API key (saved securely in `localStorage` and never sent to a backend).
   - Ability to select the model (e.g., `gemini-2.5-flash` or `gemini-2.5-pro`) and toggle between "Real AI Mode" and "Interactive Demo Mode".
2. **Interactive Chips/Tags Input**:
   - Replace standard text inputs/textareas for **Allergies**, **Ingredients**, **Kitchen Equipment**, and **Meal Goals** with a beautiful chip-input system.
   - Users can type an item and press `Enter` or `,` to create a chip.
   - Include a **"Quick Add" drawer** for common available ingredients (e.g., Chicken, Eggs, Rice, Spinach, Broccoli, Garlic) to minimize typing.
3. **Interactive Step-by-Step Cooking Mode**:
   - Each meal recipe (Breakfast, Lunch, Dinner) will feature a **"Start Cooking"** button.
   - Clicking it opens an overlay focusing on one step at a time with checkable substeps, a visual timer for timed instructions, and large legible typography.
4. **Interactive Shopping Checklist**:
   - The consolidated grocery list will be grouped by category (Produce, Pantry, Dairy, Meat/Seafood, etc.) with custom Lucide icons.
   - Items will have interactive checkboxes, an automated progress bar (*"3/8 items checked"*), and a *"Copy List"* button.
5. **Visual Budget Analysis & Feasibility**:
   - Visual gauge progress bar displaying budget utilization.
   - Clean breakdown cards comparing estimated ingredient cost vs. daily target budget, complete with dynamic feasibility statuses (Under Budget, On Target, Over Budget).
6. **In-App Saved Plan History**:
   - A side-drawer or dedicated section showcasing previous plans saved via the `dataSdk`.
   - Users can reload or delete past saved plans instantly, making the history actually functional in-app.

---

## Proposed Changes

### CulinaryAI Single-Page Application

#### [NEW] [index.html](file:///C:/Users/RAPOD/.gemini/antigravity/scratch/ai-cooking-meal-planner/index.html)
A complete rewrite of the single-page application integrating all elements:
- Rich typography, responsive layout, glassmorphic styles.
- Custom tag inputs for allergies, available ingredients, kitchen equipment, and meal goals.
- Settings panel for Gemini API Key configuration.
- Interactive tab views for Meals, Grocery List, Substitutions, Budget, and Saved History.
- Core JS logic implementing client-side Gemini API query with prompt construction, response JSON parsing, and dynamic UI rendering.
- Robust, detailed mock planning engine fallback that generates context-aware recipes when no API key is provided.

---

## Verification Plan

### Manual Verification
1. **Layout & Responsiveness**:
   - Verify premium look, hover states, transitions, and text readability.
   - Check responsiveness on simulated mobile, tablet, and desktop viewports.
2. **Interactive Controls**:
   - Test adding and deleting chips for available ingredients, allergies, equipment, and goals.
   - Verify checking off items in the grocery list updates the progress bar.
   - Open and test the step-by-step cooking mode, verifying next/back controls and the timer.
3. **Gemini API Call Integration**:
   - Enter a valid Gemini API key, enable Real AI Mode, and generate a meal plan.
   - Verify the request succeeds, returns the correct structured JSON, and displays properly in the UI.
4. **Demo / Mock Simulator Fallback**:
   - Disable API key or toggle Demo Mode.
   - Ensure a highly custom, realistic, and formatted plan is rendered instantly based on the user's specific inputs (such as dietary preference and servings).
5. **Data SDK History Integration**:
   - Click "Save Plan" and verify it adds to the Saved History section.
   - Reload saved plans from the history list and verify the UI updates correctly.
