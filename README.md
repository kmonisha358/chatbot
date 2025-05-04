import pandas as pd
df = pd.read_csv("/content/food ingredient.csv")
ingredients_data = dict(zip(df['Dish Name'].str.lower(), df['Ingredients']))

# Function to get ingredients
def get_ingredients(food_name
    food = food_name.lower().strip()  
    return ingredients_data.get(food, "Sorry, I don't know the ingredients for that dish.")

# chatbot
def chatbot():
    print(" Welcome to the FoodBot! Type a dish name and I'll tell you its ingredients.")
    print("Type 'exit' to quit.\n")

    while True:
        user_input = input("You: ").strip()
        if user_input.lower() == 'exit':
            print("Bot: Goodbye!")
            break
            
        ingredients = get_ingredients(user_input)
        print("Bot: Ingredients -", ingredients)
        print()


chatbot()
