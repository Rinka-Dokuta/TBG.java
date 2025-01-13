import java.util.Random;
import java.util.Scanner;

public class Main {
    static String[] inventory = new String[10]; // Inventory can hold up to 10 items

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in); // Used for user input
        int room = 1; // Starting room
        boolean roomTwoFight = true;
        boolean winCondition = true;
        String direction;
        String winner;

        for (int i = 0; i < 10; i++) {
            inventory[i] = " "; // Initialize each inventory slot to empty
        }
        inventory[3] = "potato"; // Give user a potato!

        while (winCondition) { // Game loop
            System.out.println("Your inventory:");
            for (int i = 0; i < 10; i++) {
                System.out.print(inventory[i]);
                System.out.print(" ");
            }
            System.out.println(" ");
            switch (room) {
                case 1: // Room 1
                    System.out.println("You are in 'Room One', do you wish to go east towards 'Room Two'?");
                    if (!inventory[0].equals("sword")) {
                        inventory[0] = "sword";
                        System.out.println("You got a sword!");
                    }
                    direction = scanner.nextLine().trim().toLowerCase();
                    if ("east".equals(direction)) {
                        room = 2;
                    } else {
                        System.out.println("Invalid direction. Staying in room " + room);
                    }
                    break;

                case 2: // Room 2
                    String monster = generateMonster();
                    if (roomTwoFight) {
                        fightMonster(monster);  // Monster fight and item drop
                        roomTwoFight = false;
                    }
                    System.out.println("You are in 'Room Two', do you wish to go south towards 'Room Three'? Or west back to 'Room One'");
                    direction = scanner.nextLine().trim().toLowerCase();
                    if ("south".equals(direction)) {
                        room = 3;
                    }
                    else if ("west".equals(direction)) {
                        room = 1;
                    }
                    else {
                        System.out.println("Invalid direction. Staying in room " + room);
                    }
                    break;

                case 3: // Room 3
                    System.out.println("You are in 'Room Three', you can go south to 'Room Four' (Cave), or north back to 'Room Two'");
                    direction = scanner.nextLine().trim().toLowerCase();
                    if ("south".equals(direction)) {
                        room = 4;
                    }
                    else if ("north".equals(direction)) {
                        room = 2;
                    }
                    else {
                        System.out.println("Invalid direction. Staying in room " + room);
                    }
                    break;

                case 4: // Room 4
                    System.out.println("You are in 'Room Four' (Cave), you can go east to 'Room Five', or north back to 'Room Three'");
                    direction = scanner.nextLine().trim().toLowerCase();
                    if ("east".equals(direction)) {
                        room = 5;
                    }
                    else if ("north".equals(direction)) {
                        room = 3;
                    }
                    else {
                        System.out.println("Invalid direction. Staying in room " + room);
                    }
                    break;

                case 5: // Room 5
                    System.out.println("You are in 'Room Five', you can go west back to 'Room Four' or Type 'i love cats' to win");
                    direction = scanner.nextLine().trim().toLowerCase();
                    if ("west".equals(direction)) {
                        room = 4;
                    }
                    else if ("i love cats".equals(direction)) {
                        System.out.println("YOU WON!");
                        winCondition = false;
                    }
                    else {
                        System.out.println("Invalid direction. Staying in room " + room);
                    }
                    break;
            } // End of switch
        } // End of game loop
    } // End of main

    // Monster generator function
    public static String generateMonster() {
        Random rand = new Random();
        String[] names = {"Goblin", "Skeleton", "Orc"};
        int index = rand.nextInt(names.length);
        return names[index];
    }

    // Battle system function with item drop
    public static void fightMonster(String monster) {
        Random rand = new Random();
        int damage = rand.nextInt(10) + 5; // Simulates damage dealt

        System.out.println("A wild " + monster + " appears!");
        System.out.println("You deal " + damage + " damage and defeat the " + monster + "!");

        // Drop a random item
        String droppedItem = weaponGen();
        addItemToInventory(droppedItem);
        System.out.println("You found a " + droppedItem + "!");
    }

    // Item generator function
    public static String weaponGen() {
        String[] chestItems = {"Sword", "Spear", "Trident", "Bow", "Godly Bolt"};
        Random random = new Random();
        int randomIndex = random.nextInt(chestItems.length);
        return chestItems[randomIndex];
    }

    // Add the item to the player's inventory
    public static void addItemToInventory(String item) {
        for (int i = 0; i < inventory.length; i++) {
            if (inventory[i].equals(" ")) { // If there's an empty slot in inventory
                inventory[i] = item;
                break;
            }
        }
    }
}
