:show-content:

========
Expenses
========

Odoo **Expenses** streamlines the management of expenses. After an employee submits their expenses
in Odoo, they are reviewed by management and accounting teams. Once approved, payments can then be
processed, and disbursed back to the employee for reimbursement.

.. seealso::
   `Odoo Expenses: product page <https://www.odoo.com/app/expenses>`_

Set expense categories
======================

The first step to track expenses is to configure the different types of expenses for the company
(managed as *expense categories* in Odoo). Each category can be as specific or generalized as
needed. Go to :menuselection:`Expenses app --> Configuration --> Expense Categories` to view the
current expensable categories in a default list view.

.. image:: expenses/categories.png
   :align: center
   :alt: Set expense costs on products.

To create a new expense category, click :guilabel:`New`. A product form will appear, with the
description field labeled :guilabel:`Product Name`.

.. note::
   Expense categories are managed like products in Odoo. The expense category form follows the
   standard product form in Odoo, and the information entered is similar. Expense products will be
   referred to as expense categories throughout this document since the main menu refers to these as
   :guilabel:`Expense Categories`.

Only two fields are required, the :guilabel:`Product Name` and the :guilabel:`Unit of Measure`.
Enter the :guilabel:`Product Name` in the field, and select the :guilabel:`Unit of Measure` from the
drop-down menu (most products will be set to :guilabel:`Units`).

.. tip::
   The *Sales* app is where specification on the units of measure are created and edited (e.g.
   units, miles, nights, etc.). Go to :menuselection:`Sales app --> Configuration --> Settings` and
   ensure `Units of Measure` is enabled in the `Product Catalog` section. Click on the
   :guilabel:`Units of Measure` internal link to :doc:`view, create, and edit the units of measure
   <../inventory_and_mrp/inventory/product_management/product_replenishment/uom>`.

.. image:: expenses/new-expense-product.png
   :align: center
   :alt: Set expense costs on products.

The :guilabel:`Cost` field on the product form is populated with a value of `0.00` by default. When
a specific expense should always be reimbursed for a particular price, enter that amount in the
:guilabel:`Cost` field. Otherwise, leave the :guilabel:`Cost` set to `0.00`, and employees will
report the actual cost when submitting an expense report.

.. note::
   The :guilabel:`Cost` field is always visible on the expense category form, but the
   :guilabel:`Sales Price` field is *only* visible if the :guilabel:`Sales Price` is selected under
   the :guilabel:`Re-Invoice Expenses` section. Otherwise, the :guilabel:`Sales Price` field is
   hidden.

.. example::
   Here are some examples for when to set a specific :guilabel:`Cost` on a product vs. leaving the
   :guilabel:`Cost` at `0.00`:

   - **Meals**: set the :guilabel:`Cost` to `0.00`. When an employee logs an expense for a meal,
     they enter the actual amount of the bill and will be reimbursed for that amount. An expense for
     a meal costing $95.23 would equal a reimbursement for $95.23.
   - **Mileage**: set the :guilabel:`Cost` to `0.30`. When an employee logs an expense for
     "mileage", they enter the number of miles driven in the :guilabel:`Quantity` field, and are
     reimbursed 0.30 per mile they entered. An expense for 100 miles would equal a reimbursement for
     $30.00.
   - **Monthly Parking**: set the :guilabel:`Cost` to `75.00`. When an employee logs an expense for
     "monthly parking", the reimbursement would be for $75.00.
   - **Expenses**: set the :guilabel:`Cost` to `0.00`. When an employee logs an expense that is not
     a meal, mileage, or monthly parking, they use the generic :guilabel:`Expenses` product. An
     expense for a laptop costing $350.00 would be logged as an :guilabel:`Expenses` product, and
     the reimbursement would be for $350.00.

Select an :guilabel:`Expense Account` if using the Odoo *Accounting* app. It is recommended to check
with the accounting department to determine the correct account to reference in this field as it
will affect reports.

Set a tax on each product in the :guilabel:`Vendor Taxes` and :guilabel:`Customer Taxes` fields, if
applicable. It is considered good practice to use a tax that is configured with :ref:`Tax Included
in Price <taxes/included-in-price>`. Taxes will be automatically configured if this is set.

.. _expenses/reimburse:

Reimburse employees
===================

After an expense report is posted to an accounting journal, the next step is to reimburse the
employee. To view all the expense reports to pay, go to :menuselection:`Expenses app --> Expense
Reports --> Reports To Pay`.

.. image:: expenses/reports-to-pay.png
   :align: center
   :alt: View reports to pay by clicking on expense reports, then reports to pay.

Just like approvals and posting, expense reports can be paid in two ways (individually or several at
once). To pay multiple expense reports at once, remain in the list view. First, select the reports
to pay by ticking the checkbox next to each report, or tick the checkbox next to
:guilabel:`Employee` to select all the reports in the list. Next, click :guilabel:`Register
Payment`.

.. image:: expenses/register-payment.png
   :align: center
   :alt: Post multiple reports by selecting them, clicking the gear, and then post the entries.

To pay an individual report, click on a report to go to a detailed view of that report. Click
:guilabel:`Register Payment` to pay the employee.

A :guilabel:`Register Payment` pop-up appears, and the :guilabel:`Journal`, :guilabel:`Payment
Method`, and :guilabel:`Payment Date` can be modified, if needed. When the selections are correct,
click :guilabel:`Create Payment` to send the payment to the employee.

To pay an individual report, click on a report in the list view to go to a detailed view of that
report. Click :guilabel:`Register Payment` to pay the employee. A :guilabel:`Register Payment`
pop-up appears, but when paying an individual expense report instead of several at once, more
options appear in the pop-up. In addition to the :guilabel:`Journal`, :guilabel:`Payment Method`,
and :guilabel:`Payment Date` fields, a :guilabel:`Recipient Bank Account`, :guilabel:`Amount`, and
:guilabel:`Memo` field appear. Select the employee's bank account from the drop-down menu to
directly deposit the payment to their account. When all other selections are correct, click
:guilabel:`Create Payment` to send the payment to the employee.

.. image:: expenses/two-payment-posting-options.png
   :align: center
   :alt: Different options appear when registering an individual expense report versus multiple
         expense reports at once.

.. seealso::
   - :doc:`expenses/approve_expenses`
   - :doc:`expenses/log_expenses`
   - :doc:`expenses/expense_reports`
   - :doc:`expenses/post_expenses`
   - :doc:`expenses/reinvoice_expenses`

.. toctree::
   :titlesonly:

   expenses/approve_expenses
   expenses/log_expenses
   expenses/expense_reports
   expenses/post_expenses
   expenses/reinvoice_expenses
