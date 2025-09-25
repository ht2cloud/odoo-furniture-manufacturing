# MRP

**MRP --> It is a system that calculates what materials are needed in what quantities and at what times to be able to manufacture finished products**

## ROUTES

Before diving fully into product manufacturing, we have to define the part that connects all our modules. The routes.

**A route is a logistics rule that defines how a product moves within the company.**

To activate routes we have to perform the same procedure as with warehouses. You have to activate multi-stage routes right next to warehouses.

![Screenshot step 1](images/Conf-rutas.png).

Once the configuration is activated, it is very important to analyze the company warehouses, the existing routes, and make a diagram of the process our product will follow. 

Here I leave explained and with a diagram that I have made to have the greatest idea of the pipeline that our product will follow. 

![Screenshot step 1](images/Flujo.png).

1. Raw Materials → Production

    -Action: Pull from.
    -Source: WH01/Raw materials.
    -Destination: WH01/Production.
    📌 Allows that when launching a production order, Odoo pulls materials from the Raw Materials warehouse.

2. Production → Semi-finished

    -Action: Push to.
    -Source: WH01/Production.
    -Destination: WH01/Semi-finished.
    📌 Simulates that the raw materials have finished the manufacturing process (semi-finished) and are sent to their location.

3. Semi-finished → Production 

    -Action: Pull from.
    -Source: WH01/Semi-finished.
    -Destination: WH01/Production.
    📌 Semi-finished products are brought to production to assemble a finished product.

4. Production → Finished products

    -Action: Push to.
    -Source: WH01/Production.
    -Destination: WH01/Finished Product.
    📌 Moves finished products to the finished goods warehouse ready for sale.

5. Finished product → Shipping

    -Action: Pull from.
    -Source: WH01/Finished product.
    -Destination: WH01/Shipping.
    📌 Moves the already sold product towards the shipping area.


**WITH THESE ROUTES WE WOULD ALREADY HAVE THE COMPLETE FLOW Purchase → Raw Materials → Production → Finished → Shipping → Customer **

![Screenshot step 1](images/Creacion-ruta.png).

We prepare our route, the lower part of rules add line is super important. A form will open, where we are going to fill in depending on the type of operation and the action we want to do. 

Since it will be a flow, the vast majority will be pulls "Pull from". Except for customer returns which will be push to the returns warehouse.

![Screenshot step 1](images/ruta-definida.png).


## BOM

Before diving into manufacturing orders and work orders, we are going to focus on the BOM. The BOM is the breakdown of a product.
That is, the materials that make up a product. Except for raw materials, all will have a BOM. For example, semi-finished products although they are not directly sellable. They are composed of several raw material elements.
In our case, we have defined the varnished pieces, and their BOM is a cut board and 1 liter of varnish. The cut board we have defined is made using 5m of oak wood to get 1 meter.


In Manufacturing -> Products -> Bill of Materials we will find to make the BOM.

**You have to keep in mind that everything in an industry are process flows. From raw material, semi-finished products are prepared, these are going to be the ones that make up the finished products ready for sale**

![Screenshot step 1](images/Creacion-bom.png).

While we assign the BOM, we are also going to prepare the "Operations" which are the actions that will be performed at the workstations to develop the material. When we have defined the materials and the quantity in each BOM. We are going to proceed to operations. 


![Screenshot step 1](images/Operaciones.png).

Here in operations we are going to define the action that is done in each workplace and the estimated time it takes to perform the action.

Later in the BOMs we are going to define what type of operation the BOM has. It is important, as it serves us to indicate if we are manufacturing a semi-finished or a finished product.
In our warehouse configuration, semi-finished products go in one location and finished products go in another.

## MO (MANUFACTURING ORDER) WO (WORK ORDER)

-The acronyms MO -> means manufacturing order and WO -> work order.

-Next, we are going to proceed to create manufacturing orders. In manufacturing orders, later we are going to link with orders, they mark how many units have to be manufactured. Rather, the order is passed to the factory so they can manufacture it.

-First of all we are going to select the item we want, there the BOM will be displayed.
![Screenshot step 1](images/MO.png).
-Next step when we see that everything is correct is to confirm it. It will create an automatic sequence number that will be the order number. 
-We are going to select the components and we are going to check if there is availability 
![Screenshot step 1](images/MO-1.png).

-Once we have seen that there is availability, we are going to proceed to click plan, so that the Work Orders are set in motion.

-We go to the Orders-> Work orders section. And there, we are going to see all the work orders that exist. If it says ready as in our case, it means that the components are already prepared, that is, they are already in the location prepared to assemble. If this were not the case, a transfer would have to be made, or the route would not be well configured.

-We start the orders and we will see that a counter starts, it is a simulation of the time it takes to make the order. As before in the work centers we have established that the average time is calculated based on the last 4.
![Screenshot step 1](images/OT.png).
-We mark it as done, since we are in a demo

Once we have finished with the orders, we proceed to the manufacturing orders and we are going to see that it says to close. We just go in and click produce all, so Odoo is going to make the stock transfers. Subtract raw materials, add or subtract semi-finished products and/or add finished products. 

![Screenshot step 1](images/CerrarMO.png).

**Finally we are going to check if the finished product has been created **

![Screenshot step 1](images/Comprobar.png).


**NOW WE ARE GOING TO SEE THE NEXT STEP WHICH IS SALES, TO BE ABLE TO INCREASE THIS FLOW**





