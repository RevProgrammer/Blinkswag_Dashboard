Estimate
========

.. _installation:

 

Function: convert_estimate_to_so
---------------------------------

**Module**: Estimate

**Function**: convert_estimate_to_so

**Workflow Rule**: Convert Estimate To SO



Description : This code is used to take information from an estimate in Zoho Books and create a new sales order using that information. The script starts by retrieving the estimate ID and organization ID and then goes on to get more detailed information about the estimate, such as the project ID, contact persons, and other details. It then takes the line items from the estimate and updates their custom fields. The script also updates the custom fields of the estimate itself. Finally, it creates a new sales order using the information gathered from the estimate.

It basically is a way to automate the process of converting an estimate to a sales order in Zoho Books, it eliminates the need for manual entry of data and saves time.

* The script starts by getting the "estimate_id", "organization_id" and "customer_id" from the estimate object.

* Then, it uses the "zoho.books.getRecordsByID" method to retrieve detailed information about the estimate using the organization ID and estimate ID. It stores this     detailed information in the "estimate_detailed" variable.

* Next, the script checks if the estimate is associated with a project and if so, it gets the project ID and assigns it to the "project_id" variable.

* The script then gets information about the estimate such as whether the discount is applied before tax, contact persons, estimate number, discount amount, discount     type, and salesperson ID.

* The script also retrieves the line items of the estimate and stores it in the "estimate_line_items" variable.

* For each line item, it retrieves the custom fields and updates the label and value of each custom field. It also adds the project ID to the line item.

* Then, the script makes a GET request to the Zoho Books API to retrieve the custom fields of sales orders.

* It then iterates through each custom field of the estimate and for each custom field that is active, has the same data type and label as the sales order custom         field, it adds the custom field to the list of updated custom fields for the sales order.

* Finally, the script creates a new sales order using the updated information such as line items and custom fields.

To use Lumache, first install it using pip:

.. code-block:: console

   (.venv) $ pip install lumache

Creating recipes
----------------

To retrieve a list of random ingredients,
you can use the ``lumache.get_random_ingredients()`` function:

.. autofunction:: lumache.get_random_ingredients

The ``kind`` parameter should be either ``"meat"``, ``"fish"``,
or ``"veggies"``. Otherwise, :py:func:`lumache.get_random_ingredients`
will raise an exception.

.. autoexception:: lumache.InvalidKindError

For example:

>>> import lumache
>>> lumache.get_random_ingredients()
['shells', 'gorgonzola', 'parsley']

