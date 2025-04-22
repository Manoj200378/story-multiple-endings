# story-multiple-endings
def get_choice(options):
    options_lower = [opt.lower() for opt in options]
    while True:
        choice = input("→ What do you do? ").strip().lower()
        if choice in options_lower:
            return choice
        print(f"Sorry, I didn't understand that. Try: {', '.join(options)}")

def start():
    print("\n The sun rises over a strange land you've never seen before.")
    print("You're standing at a crossroads—one path leads into a dark forest, the other toward a quiet village.")
    print("Do you want to go to the **forest** or head toward the **village**?")

    choice = get_choice(["forest", "village"])

    if choice == "forest":
        forest_path()
    elif choice == "village":
        village_path()

def forest_path():
    print("\n The forest is thick and silent. The air feels heavy.")
    print("Suddenly, you hear a low growl. A **wolf** appears on the trail, watching you.")
    print("You also see a sturdy old **tree**—climbable, if you're fast.")
    print("Do you try to **follow the wolf**, or quickly **climb the tree**?")

    choice = get_choice(["follow the wolf", "climb the tree"])

    if choice == "follow the wolf":
        bad_end()
    elif choice == "climb the tree":
        good_end()

def village_path():
    print("\n🏘 You stroll into the village, greeted by the smells of fresh bread and wood smoke.")
    print("To your left, an **old man** in a long cloak waves you over.")
    print("To your right, a fruit stall stands unattended—ripe **apples** glisten in the morning sun.")
    print("Do you **talk to the old man**, or quietly **steal an apple**?")

    choice = get_choice(["talk to the old man", "steal an apple"])

    if choice == "talk to the old man":
        mystery_end()
    elif choice == "steal an apple":
        jail_end()

def bad_end():
    print("\n You follow the wolf deeper into the woods...")
    print("...until you're surrounded by glowing eyes. It's a trap.")
    print("You shouldn't have trusted the beast.\n")
    print(" **BAD END: The forest claimed you.**")

def good_end():
    print("\n You scramble up the tree just as the wolf lunges.")
    print("From the treetop, you spot a nearby rescue team searching for you.")
    print("You wave—and they see you!\n")
    print(" **GOOD END: You are safe at last.**")

def mystery_end():
    print("\n The old man leans in close. 'The real journey is still ahead,' he whispers.")
    print("In a blink, he vanishes—leaving behind only a riddle carved into the dirt.\n")
    print(" **MYSTERY END: You've unlocked something deeper...**")

def jail_end():
    print("\n You slip an apple into your bag... but a firm hand grabs your shoulder.")
    print("The town guard hauls you off. Stealing, even something small, has consequences.\n")
    print(" **JAIL END: Actions have consequences.**")

def main():
    print(" Welcome to *Whispers of the Wandering Road* – An Interactive Adventure!")
    while True:
        start()
        again = input("\n Would you like to play again? (yes/no): ").strip().lower()
        if again != "yes":
            break
    print("\n Farewell, traveler. Until your next adventure.")

if __name__ == "__main__":
    main()
