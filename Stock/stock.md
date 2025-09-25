# STOCK

## WAREHOUSES

Before dedicating ourselves to creating stock, the essential part is to create the warehouses. To be able to structure the integration of this module much better. We are going to configure from warehouse -> locations -> product category -> product.

In the inventory part we go to Settings configuration -> Warehouses and once we are there we will proceed to create our 4 Warehouses.
![Screenshot step 1](images/Almacen-create.png).

In warehouse creation, it is important to distinguish the needs and capabilities of the company where we implement Odoo. In this example, I have considered that it will have 1 Warehouse.

- Raw Materials.

This is important because you have to associate how it will be replenished whether in purchase, manufacturing or rather with transfers between centers. 
Therefore, depending on what type of warehouse, it will do it one way or another. Example: The raw materials one, as it is composed of raw materials basically it will be through purchases. On the other hand, the Production one will be through manufacturing. And the shipping one through transfers from Central.

![Screenshot step 1](images/Almacen-List.png).

## UBICACIONES.

## LOCATIONS

Una vez comprobamos que nuestros almacenes estan creados correctamente. Vamos a por la otra parte importante, las ubicaciones internas que tiene cada almacén. 

To understand the procedure a bit, I have divided my warehouses as follows:


**-FurnitureCortes -- CENTRAL.(WH01)**

    -WH01/Raw materials.
    -WH01 Finished goods.
    -WH01/Shipping.

It is the company's general warehouse, from where everything is divided. Raw materials and finished goods are stored, pickings are made.  

Location creation. It is important to say what type of location it is.

Attached is a list of the types of locations there are.
Types of locations in Odoo

**Internal** 

    -Represents a physical place within the company.

    Example: Raw materials, Production, Finished products.

    -Used in most flows (consumption, manufacturing, storage).

**Vendor**

    -Used as the source of products when you make a purchase.

    Example: "Vendor" → FurnitureCortes/Raw Materials/Reception.

**Customer** 

    -Used as destination when you make a sale.

    Example: FurnitureCortes/Shipping/Shipment → Customer.

**Transit** 

    -Represents goods in transit (between warehouses).

    Example: from Central Warehouse to Regional Warehouse.

**Return** 

    -Used to register returned products.

    Example: FurnitureCortes/Shipping/Returns.

**Inventory** 

    -Used in stock adjustments (losses, breakages, inventory differences).


![Screenshot step 1](images/Ubicaciones.png).

![Screenshot step 1](images/Ubicaciones-tipo.png).


## STOCK CREATION

The next step in our flow is stock creation. First of all, we are going to create the categories so when defining the articles we are going to assign the category to which they belong.

-We will divide into 3 categories: Raw material, semi-finished, finished.

To create the categories we will go to Settings-> Product categories.

![Screenshot step 1](images/Categoria-producto.png).

Once we have the categories created, we will go to the product section and click new.

There we will create the article, we will set the characteristics it should have, the units of measure (They are activated next to locations in configuration) the category and we will indicate in update quantity if we have initial stock already in warehouse. 

![Screenshot step 1](images/Crear-stock.png).

Finally we will assign the initial location (if it has stock).


![Screenshot step 1](images/Stock-Ubicacion.png).

Finally we see in the stock.

-The elements that come by default from Odoo and the 3 raw material articles created: Screw, Varnish and Wood.

![Screenshot step 1](images/lista-stock.png).


**WHEN WE HAVE CREATED THE PRODUCTS WE ARE GOING TO SET THEIR LOCATION IN WH01. ACCORDING TO THE TYPE OF PRODUCT IT IS, IT WILL GO IN ONE LOCATION OR ANOTHER**