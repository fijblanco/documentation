========================
Main accounting concepts
========================

Double-entry bookkeeping
========================

Odoo automatically creates all the underlying journal entries for each of your accounting
transactions (e.g. such as customer invoices, vendor bills, point-of-sales orders, expenses,
inventory valuations etc.).
Odoo uses the double-entry bookkeeping system, whereby every entry needs a corresponding and
opposite counterpart in a different account, with one account debited and the other credited.
It ensures that all transactions are recorded accurately and consistently and that the accounts
always balance.

.. seealso::
   :doc:`Accounting Cheat Sheet <cheat_sheet>`

Accrual and cash basis
======================

Both accrual and cash basis accounting are supported in Odoo. This allows reporting income and
expense either when the transaction occurs (accrual basis) or when the payment is made or received
(cash basis).

.. seealso::
   :doc:`Cash basis <../taxation/taxes/cash_basis_taxes>`

Multi-company
=============

Several companies can be managed within the same database. Each company has its
:doc:`chart of accounts <initial_configuration/chart_of_accounts>`, also useful to generate
consolidation reports. Users can access several companies but can only work on a single company's
accounting at a time.

Multi-currency environment
==========================

A :doc:`multi-currency <../others/multi_currency>` environment with an automated
exchange rate to ease international transactions is available in Odoo. Every transaction is recorded
in the company's default currency; for transactions occurring in another currency, Odoo stores both
the value in the company's currency and the transactions' currency value. Odoo generates currency
gains and losses after reconciling the journal items.

.. seealso::
   :doc:`Manage a bank in a foreign currency <../bank/setup/foreign_currency>`

International standards
=======================

Odoo Accounting supports more than 70 countries. It provides the central standards and mechanisms
common to all nations, and thanks to country-specific modules, local requirements are fulfilled.
Fiscal positions exist to address regional specificities like the chart of accounts, taxes, or any
other requirements.

.. seealso::
   :doc:`Fiscal localization packages <../../fiscal_localizations>`

Accounts receivable and payable
===============================

By default, there is a single account for the account receivable entries and one for the account payable
entries. As transactions are linked to your **contacts**, you can run a report per customer, vendor,
or supplier.

The **Partner Ledger** report displays the balance of your customers and suppliers. It is available
by going to :menuselection:`Accounting --> Reporting --> Partner Ledger`.

Reporting
=========

The following financial :doc:`reports <../reporting/overview/main_reports>` are available and
updated in real-time:

+-----------------------------------------------+
|               Financial reports               |
+============+==================================+
| Statement  | Balance sheet                    |
|            +----------------------------------+
|            | Profit and loss                  |
|            +----------------------------------+
|            | Cash flow statement              |
|            +----------------------------------+
|            | Tax report                       |
|            +----------------------------------+
|            | ES sales list                    |
+------------+----------------------------------+
| Audit      | General ledger                   |
|            +----------------------------------+
|            | Trial balance                    |
|            +----------------------------------+
|            | Journal report                   |
|            +----------------------------------+
|            | Intrastat report                 |
|            +----------------------------------+
|            | Check register                   |
+------------+----------------------------------+
| Partner    | Partner ledger                   |
|            +----------------------------------+
|            | Aged receivable                  |
|            +----------------------------------+
|            | Aged payable                     |
+------------+----------------------------------+
| Management | Invoice analysis                 |
|            +----------------------------------+
|            | Unrealized currency gains/losses |
|            +----------------------------------+
|            | Depreciation schedule            |
|            +----------------------------------+
|            | Disallowed expenses              |
|            +----------------------------------+
|            | Budget analysis                  |
|            +----------------------------------+
|            | Product margins                  |
|            +----------------------------------+
|            | 1099 report                      |
+------------+----------------------------------+

.. tip::
   You can :doc:`create and customize reports <../reporting/overview/customize>` with Odoo's report
   engine.

Tax report
----------

Odoo computes all accounting transactions for the specific tax period and uses these totals to
calculate the tax obligation.

.. important::
  Once the tax report has been generated for a period, Odoo locks it and prevents the creation of
  new journal entries involving VAT. Any correction to customer invoices or vendor bills has to
  be recorded in the next period.

.. note::
   Depending on the country's localization, an XML verion of the tax report can be generated to  be
   uploaded to the VAT platform of the relevant taxation authority.

Bank synchronization
====================

The bank synchronization system directly connects with your bank institution to automatically
import all bank transactions into your database. It gives an overview of your cash flow without
having to log into into an online banking system or wait for paper bank statements.

.. seealso::
   :doc:`Bank Synchronization <../bank/bank_synchronization>`

Inventory valuation
===================

Both periodic (manual) and perpetual (automated) inventory valuations are supported in Odoo. The
available methods are standard price, average price, :abbr:`LIFO (Last-In, First-Out)` and
:abbr:`FIFO (First-In, First-Out).`

.. seealso::
   :doc:`View the impact of the valuation methods on transactions
   </applications/inventory_and_mrp/inventory/management/reporting/inventory_valuation_config>`

Retained earnings
=================

Retained earnings are the portion of income retained by a business. Odoo calculates current year
earnings in real-time, so no year-end journal or rollover is required. The profit
and loss balance is automatically reported on the balance sheet report.

.. seealso::
   :doc:`Accounting Cheat Sheet <cheat_sheet>`

Fiduciaries
===========

The :guilabel:`Accounting Firms` mode can be activated by going to :menuselection:`Accounting -->
Configuration --> Settings --> Accounting Firms mode`. When enabled:

- The document's sequence becomes editable on all documents;
- A new field :guilabel:`Total (tax incl.)` appears in order to speed up and control the encoding by
  automating line creation with the right account and tax;
- :guilabel:`Invoice Date` and :guilabel:`Bill Date` are pre-filled when encoding a transaction.
- A :guilabel:`Quick encoding` option is available for customer invoices and vendor bills.
