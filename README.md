# Greedy Algorithm Project


### Objective

In this project, our objective is to understand how to use the Greedy algorithm

### Problem   

Imagine you have a truck and a list of items, you should fill the truck with the most valued items. Note that the truck capacity is only 100kg.

- Items list:
  
Item 1:   
weight: 50kg    
value: 4000$    
   
Item 2:    
weight: 30kg    
value: 3000$    
   
Item 3:    
weight: 20kg     
value: 2000$     
   
Item 3:    
weight: 10kg     
value: 1500$     
   
- Solution:
   
Using Greedy algorithm.    
1. Pick the most valuable item that will fit in your truck.
2. Pick the next most valuable item that will fit in your truck. And so on.
   
- Result:
   
Item 1:   
weight: 50kg    
value: 4000$    
   
Item 2:    
weight: 30kg    
value: 3000$    
   
Item 3:    
weight: 20kg     
value: 2000$        
   
### Implementation

* Add an **if** statement that picks the most valuable item in the array.
* Write the If statement conditions considering the truck capacity and the item value.
* In the if statement **currentItem** should hold the current most valuable item.
* In the if statement **removeIndex** should hold the current most valuable item index.



```java


class Item {

    String name;
    int value;
    int weight;

    Item(String itemName, int value, int weight){
        this.name = itemName;
        this.value = value;
        this.weight = weight;
    }
    
}


public class TruckShipments {

    int capacity = 100;
    Item [] items = {(new Item("item 1", 4000, 50)), (new Item("item 2", 3000, 30)), (new Item("item 3", 2000, 20)), (new Item("item 4", 1500, 10))};


    public Item[] greedyAlgorithm() {

        Item plan[] = new Item[this.items.length];
        Item[] temp_item_arr = this.items;
        Item currentItem = temp_item_arr[0];
        int currentCapacity = 0;

        // counter for plan [] 
        int k = 0;
        // index of the element to delete
        int removeIndex = 0;

        while (currentCapacity < this.capacity && k < plan.length) {

            // find the most valuable item that fits the truck capacity
            for (int i = 0; i < temp_item_arr.length; i++) {

                /* add your code here */

            }

            plan[k++] = currentItem;
            currentCapacity += currentItem.weight;
            delete(temp_item_arr, removeIndex);
            currentItem = temp_item_arr[0];
        }

        return plan;
    }

    public Item[] delete(Item[] temp_item_arr, int elementIndex) {

        for (int i = elementIndex; i < temp_item_arr.length - 1; i++) {
            temp_item_arr[i] = temp_item_arr[i + 1];
        }

        return temp_item_arr;

    }

    public void display() {
        for (Item item : items) {
            System.out.println("Name: " + item.name + " Time: " + item.weight + " Score: " + item.value);

        }
    }

    public void displayPlan(Item plan[]) {

        for (Item item : plan)
            if (item != null)
                System.out.println("Name: " + item.name + " Time: " + item.weight + " Score: " + item.value);

    }

    public static void main(String[] args) {
        TruckShipments ts = new TruckShipments();

        System.out.println();
        System.out.println("List of places : ");
        ts.display();

        System.out.println();

        Item[] plan = ts.greedyAlgorithm();
        System.out.println("Plan : ");
        ts.displayPlan(plan);
        System.out.println();

    }


}

  ```
