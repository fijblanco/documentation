================================================
Invoice based on delivered or ordered quantities
================================================

Different business policies might require different options for invoicing:

- The *Invoice what is ordered* rule is used as the default mode in Odoo *Sales*, which means
  customers are invoiced once the sales order is confirmed.

- The *Invoice what is delivered* rule invoices customers once the delivery is done. This rule
  concerns businesses that sell materials, liquids, or food in large quantities. In these cases,
  the quantity might diverge a little bit, and it is, therefore, preferable to invoice the quantity
  actually delivered.

Being able to have different invoicing options provides more flexibility.

Invoicing policy features
=========================

To activate the necessary invoicing policy features, go to :menuselection:`Sales app -->
Configuration --> Settings`, and under the :guilabel:`Invoicing` heading, select a
:guilabel:`Invoicing Policy` rule: :guilabel:`Invoice what is ordered` or
:guilabel:`Invoice what is delivered`.

.. image:: invoicing_policy/invoicing-policy-1.png
   :align: center
   :alt: How to choose your invoicing policy on Odoo Sales.

.. important::
   If you decide to choose the :guilabel:`Invoice what is delivered` rule, the :guilabel:`Automatic
   invoice` feature can **not** be activated, which automatically generates invoices when an online
   payment is confirmed.

Invoicing policy on product form
================================

From any product page (:menuselection:`Sales app --> Products --> Products --> Choose any desired
product), the invoicing policy option is located under the :guilabel:`General Information` tab, and
it can be changed manually.

.. image:: invoicing_policy/invoicing-policy-5.png
   :align: center
   :alt: How to change your invoicing policy on a product form on Odoo Sales.

Impact on sales flow
====================

In Odoo *Sales*, the basic sales flow starts with the creation of a quotation. Then, that quotation
is sent a customer. Next, it needs to be confirmed, which turns the quotation into a sales order.
This, in turn, creates an invoice.

The following is a breakdown of how invoicing policy rules impact the aforementioned sales flow:

- :guilabel:`Invoice what is ordered`: No impact on the basic sales flow. An invoice is created as
  soon as a sale is confirmed.

- :guilabel:`Invoice what is delivered`: Minor impact on sales flow, because the delivered quantity
  needs to be manually entered on the sales order. Or, the *Inventory* app can be installed, and
  used to confirm the delivered quantity before creating an invoice with the *Sales* app. If an
  invoice is attempted to be created, without validating the delivered quantity, the following
  error message appears.

  .. image:: invoicing_policy/invoicing-policy-3.png
     :align: center
     :alt: How the choice of your invoicing policy impacts your sales flow on Odoo Sales.

.. note::
   Once a quotation is confirmed, and the status changes from :guilabel:`Quotation sent` to
   :guilabel:`Sales order`, the delivered and invoiced quantities are available to view, directly
   from the sales order. This is true for both invoicing policy rule options.

   .. image:: invoicing_policy/invoicing-policy-4.png
      :align: center
      :alt: How to see your delivered and invoiced quantities on Odoo Sales.

   Odoo automatically adds the quantities to the invoice, even if it's a partial delivery.

Finally, to create an invoice, there are different options to choose from: *Regular invoice* or
*Down payment (percentage or fixed amount)*.

.. important::
   Be sure to check out the documentation explaining down payment options here: :doc:`down_payment`
   to learn more.
