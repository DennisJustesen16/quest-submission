1.  Explain why we wouldn't call `changeGreeting` in a script.
	1. Because a script is only used to view data, not change it.
    
2.  What does the `AuthAccount` mean in the `prepare` phase of the transaction?
	1. It is a type, your account so you can access your data.
    
3.  What is the difference between the `prepare` phase and the `execute` phase in the transaction?
	1. In the prepare phase, you access data, whereas in the execute phase, you call functions
    
4.  This is the hardest quest so far, so if it takes you some time, do not worry! I can help you in the Discord if you have questions.
    

-   Add two new things inside your contract:
    
    -   A variable named `myNumber` that has type `Int` (set it to 0 when the contract is deployed)
    -   A function named `updateMyNumber` that takes in a new number named `newNumber` as a parameter that has type `Int` and updates `myNumber` to be `newNumber`
    
    ![Pasted image 20221117194405](https://user-images.githubusercontent.com/78741323/204105931-8478a0ab-4c04-4808-a8d4-526aa983d99a.png)

-   Add a script that reads `myNumber` from the contract
    
    ![Pasted image 20221117194425](https://user-images.githubusercontent.com/78741323/204105946-62ae4e61-07b0-4d43-be7c-1aad313c1e8c.png)

-   Add a transaction that takes in a parameter named `myNewNumber` and passes it into the `updateMyNumber` function. Verify that your number changed by running the script again.
 
 ![Pasted image 20221117194440](https://user-images.githubusercontent.com/78741323/204105975-c58d02c5-5609-4d74-a6f5-2ed378c6b05b.png)
