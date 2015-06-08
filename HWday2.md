#Homework for DAT7 class 2

1. **Using `chipotle.tsv` in the `data` subdirectory:**

    **Look at the head and the tail, and think for a minute about how the data is structured. What do you think each column means? What do you think each row means? Tell me! (If you're unsure, look at more of the file contents.)**
    
    Each row represents a single food item ordered at a chipotle restaurant.
    
    The columns represent:
    * order_id is a unique identifier for each person that places an order at chipotle in this data set.
    
    * quantity refers to the amount of each listed item purchased in whole units
    
    * item_name is the name of the item in the current row that was purchased by a person in a particular order
    
    * choice_description lists the customizations and ingredients made by the consumer for a given item in an order
    
    **How many orders do there appear to be?**
    ```
    tail chipotle.tsv
    ```
    Assuming that all orders are arranged in ascending order, there are 1834 orders in the file.
    
    ```
    cut -f1,1 chipotle.tsv | uniq | wc -l
    ```
    A more thorough check also results in 1834 orders.
    
    **How many lines are in the file?**
    ```
    wc -l chipotle.tsv 
    ```
    There are 4623 lines in the file including the header.
    
    **Which burrito is more popular, steak or chicken?**
    ```
    grep -i "steak burrito" chipotle.tsv |wc -l
    ```
    There were 368 steak burritos ordered in the sample.
    ```
    grep -i "chicken burrito" chipotle.tsv |wc -l
    ```
    There were 553 chicken burritos ordered in the sample.
    Based on this sample, we conclude that chicken burritos are more popular.
    
    **Do chicken burritos more often have black beans or pinto beans?**
    ```
    grep -i "chicken burrito" chipotle.tsv |grep -i "black"|wc -l
    ```
    Of the 553 chicken burritos ordered, 282 had black beans.
    ```
    grep -i "chicken burrito" chipotle.tsv |grep -i "pinto"|wc -l
    ```
    105 chicken burritos had pinto beans.
    ```
    grep -i "chicken burrito" chipotle.tsv |grep -iv "pinto\|black"|wc -l
    ```
    186 chicken burritos were ordered without beans.
    
    We conclude, based on this sample, black beans are ordered more often than pinto beans with a chicken burrito.
    
2. **Make a list of all of the CSV or TSV files in the DAT7 repo (using a single command). Think about how wildcard characters can help you with this task.**
3. **Count the number of occurrences of the word 'dictionary' (regardless of case) across all files in the DAT7 repo.**
