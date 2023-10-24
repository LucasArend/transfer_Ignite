# Testing Transfers with the API - Ignite
<br>

## About

Challenge proposed during the NodeJS track at RocketSeat's Ignite bootcamp. This challenge was proposed in the fifth chapter of the trail and its objective was to consolidate the knowledge taught during module 5 of the course.


The new functionality should allow the transfer of amounts between accounts. To do this, you can think about the best way to build this solution, but some requirements must be met:

- It must not be possible to transfer amounts greater than what is available in an account balance;
- The balance (obtained through the route `/api/v1/statements/balance`) must also consider all amounts transferred or received through transfers when displaying a user's balance;
- The information to make a transfer will be:

    ```json
    {
    	"amount": 100,
    	"description": "Transfer description"
    }
    ```

    You can pass the `id` of the recipient user via a parameter in the route (example: `/api/v1/statements/transfers/:user_id`) and the id of the sender user can be obtained through the JWT token sent in the request header;

- When showing a user's balance, `transfer` type operations must have the following fields:

    ```json
    {
      "id": "4d04b6ec-2280-4dc2-9432-8a00f64e7930",
      "sender_id": "cfd06865-11b9-412a-aa78-f47cc3e52905",
      "amount": 100,
      "description": "Value transfer",
      "type": "transfer",
      "created_at": "2021-03-26T21:33:11.370Z",
      "updated_at": "2021-03-26T21:33:11.370Z"
    }
    ```
    
    Note the `sender_id` field. This must be the `id` of the user who sent the transfer.
    The `type` field must also display the type of the operation, which in this case is `transfer`.
