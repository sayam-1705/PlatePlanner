# PlatePlanner

## Description
A smart meal planning app that offers personalized recipe suggestions, meal plans, and nutritional insights based on user preferences.

## Features
- Ingredient-based recipe suggestions
- Customizable meal plans
- Real-time nutritional analysis
- Filter recipes by season, cuisine, and difficulty
- Weather-based meal recommendations

## Run the app
Run the app locally in any VS Code terminal
1. Open the folder "Smart Recipe Planner" with VS Code
2. Open a new terminal and write the following code
   - cd backend
   - npm run start
3. Open a new terminal and write the following code
   - cd frontend
   - npm run dev
4. In the browser enter "http://localhost:5173/"

## Routes

### User Endpoints

| Method | Route | Description | Request Parameters | Response |
|-|-|-|-|-|
| POST | `/user/register` | Register a new user | `name`, `email`, `pass`, `cPass` | `message`: `User Created`, `user`: `{ name, email }` |
| POST | `/user/login` | Log in a user | `email`, `pass` | `message`: `Login success`, `token`: `JWT token for authentication`, `user`: `{ name, email }` |
| DELETE | `/user/delete/example12345@gmail.com` | Delete a user profile | `Authorization : Bearer token`, `pass` | `message`: `User Deleted`|

### Recipe Endpoints

| Method | Route | Description | Request Parameters | Response |
|-|-|-|-|-|
| POST | `recipe/create-recipe` | Create a new recipe | `Authorization : Bearer token`, `name`, `image`, `ingredients` , `quantity`, `season`, `occasion`, `type`, `recipeType`, `time`, `difficulty`, `servings`, `instructions` | `recipe`: `{ userId, name, image, ingredients : name, quantity, calories, season, occasion, type, recipeType, time, difficulty, servings, nutritionPerServing, instructions }` |
| GET | `recipe/search` | Search recipes based on user request | `name / image / ingredients / season / occasion / type / recipeType / time / difficulty / servings / instructions` | `recipe` : `name` |
| POST | `recipe/weather-suggestions` | Suggest weather based on location | `location` | `temperature`, `weatherDescription`, `season`, `recipeType`, `recipes` |

### Nutrition Endpoint

| Method | Route | Description | Request Parameters | Response |
|-|-|-|-|-|
| POST | `/api/nutrition/nutrition-info` | Provides nutrition information about a ingredient | None | `calories` |
