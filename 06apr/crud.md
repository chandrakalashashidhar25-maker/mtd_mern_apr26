# CRUD ops
    Create Read Update Delete
    Read -> Query

# Mongo DB
'''
    Building blocks : Document 
    !JSON document (BSON)

    RDMS                      MongoDB
    Database                  Database     !Container for data 
    Table                     Collection
    Rows                      Documents
    Referential model         Referential and Embedded

'''

order
    user details + billing address _ billing details 
    + products selected in cart 
    == order info + line items 
    == { id, user_id , bill_amount , address , pay_mode , status} +
        [{ id , product_id , order_id , qty , price, amount }]
    == Referential Modeling 
        orders:
            id, user_id, bill_amt, address, pay_mode, status
            1 , 10        18000    xyz       gpay      pending

        order_items : id,   product_id,   order_id,   qty,   price,   amt
                      1    1001          1           1      16000    16000
                      2    4002          1           2      1000     2000
    in mongo 

    orders
      [
        id:1, usde_id : 10, bill_amt:18000, address:xyz, pay_mode:gpay,.....
      ]   
    order_items:[
    {id-1,  product_id-1001,   order_id-1,   qty-2,   price-16000,   amt-16000 }
    {id-2,   product_id-4002,   order_id-1,   qty-2,   price-1000,   amt-2000}
    ]