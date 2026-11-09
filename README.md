<h1 align="center">PastryShop</h1>

**English** | [Srpski](README.sr.md)

**PastryShop** is a desktop WPF application for running a bakery or pastry shop: sales through a POS screen, product and stock management, user accounts and reports. There are two roles, manager and cashier, and each one opens its own screen with its own functions after login. The rest of this document is a user guide.

<p align="center">
  <img src="images/17_blagajnik_pos.png" alt="blagajnik pos" width="290"/>
  <img src="images/08_menadzer_proizvodi.png" alt="pregled proizvoda" width="290"/>
  <img src="images/14_menadzer_zalihe.png" alt="zalihe proizvoda" width="290"/>
</p>
<p align="center"><em>Cashier POS screen · product overview · stock management</em></p>

## Key features

- **User accounts and roles** – two roles (manager and cashier); the manager adds and edits accounts, changes roles, activates and deactivates accounts, and resets passwords.
- **Products and stock** – browse, add and edit products (food, drinks, utensils), track quantities, supply batches and expiry dates.
- **POS** – create orders, work with a cart, pay by cash, by card or pay later, and cancel orders that were already created.
- **Reports and statistics** – panels and charts for sales and stock (manager) and for the logged-in cashier's work.
- **Settings** – three themes (light, dark, blue), Serbian and English UI, user profile editing.
- **Keyboard shortcuts** – for navigation and the most common actions.

---

## Roles and login

### Roles

The application has two user roles.

**Manager**
- Has administrative control over the whole system.
- Creates and manages user accounts (adding new accounts, deactivating existing ones, resetting passwords).
- Oversees products and stock.
- Has access to reports and statistics.

**Cashier**
- Uses the POS interface at the point of sale.
- Creates and pays orders and views the day's transactions.

### Login

The manager creates accounts for employees and assigns each a role and an initial password. Employees are advised to change the password on first login. On startup the login screen opens with a ***username*** and a ***password*** field. Both are required, only letters and digits are allowed, and there is a minimum and maximum length. *Tab* moves between fields.

<p align="center">
  <img src="images/01_prijava.png" alt="Dijagram" height="250" width="350"/>
</p>

The language can be changed on this screen; *Ctrl + L* opens the language drop-down. The selected language applies to the login screen only.

After clicking ***Login*** or pressing *Enter*, the app checks the credentials. If they are valid, it records the login time and opens the start screen for the user's role: managers land on the user account screen, cashiers on the POS screen.

If login fails, a warning dialog shows the reason: wrong username or password, the account is inactive, or invalid field values (in which case messages are also shown next to the fields).

The ***Cancel*** button exits the application; the shortcut is *Escape (Esc)*.

---

## Manager

The manager's main responsibilities:
- user management,
- product management,
- stock control,
- reports.

### Login and navigation

After login the manager start screen is shown.

A vertical ***navigation menu*** with icons and labels is on the left. Each item has a keyboard shortcut:

- **Employees** – view and manage user accounts (*Ctrl + U*).
- **Products** – product catalogue and editing (*Ctrl + P*).
- **Reports** – sales and inventory reports (*Ctrl + R*).
- **Settings** – language and theme (*Ctrl + S*).
- **Profile** – edit the user's profile (*Ctrl + M*).
- **Logout** – log out of the application (*Esc*).

The main area on the right shows the ***content of the selected module***: employees, stock levels, product data and reports.

### User management

#### User list

<p align="center">
  <img src="images/03_menadzer_korisnici.png" alt="pregled korisnika" height="250" width="350"/>
</p>

The manager can see all users. The table shows *ID, username* and *user type*, with icons for *account details, status change, password change* and other actions.

A ***search field*** finds users quickly (*Tab* or *F3* moves focus to it), and a drop-down ***filters by status*** (*Ctrl + F*). Users with the status *inactive* are highlighted.

#### Adding a user

The ***Add*** button in the top right corner of the main screen (*Ctrl + N*) opens a form for a new account. The form has *common fields* for all users, and *type-specific fields* that appear depending on the selected user type.

<p align="center">
  <img src="images/04_menadzer_korisnici.png" alt="dodaj korisnika" height="280" width="370"/>
</p>

**Common fields**

- *User type* – drop-down, required: *Manager* or *Cashier*,
- *Username* – required text field; must be unique, only valid characters are accepted, with minimum and maximum length,
- *Password* – required masked field with similar constraints as the username,
- *First name* – text field that accepts only letters, digits and spaces,
- *Last name* – same as first name,
- *Phone number* – text field that accepts only a valid phone number format,
- *Address* – free text,
- *Salary* – required numeric field, cannot be negative,
- *Image path (Choose image)* – file picker button; a preview is shown after selection. Allowed formats: *.jpg, .jpeg, .png*.

**Manager-only fields** (shown only when Manager is selected)

- *Department* – text field that accepts only letters, digits and spaces.

**Cashier-only fields** (shown only when Cashier is selected)

- *Register ID* – numeric field, integers only,
- *Shift start* – calendar for picking date and time; cannot be in the past,
- *Shift end* – date and time; must be after the shift start, and the shift must last at least one hour.

Input is validated before saving; if everything is valid, the new account is saved. Otherwise a warning dialog is shown, and error messages also appear next to the invalid fields.

#### User details

<p align="center">
  <img src="images/05_menadzer_korisnici.png" alt="prikaz detalja korisnika" height="250" width="350"/>
</p>

Clicking the details icon for a selected user opens a window with ***detailed information***: profile picture, user type, username, first and last name, phone number and address, hire date, salary and last login, plus data specific to the type (department for a manager, register ID and shift for a cashier).

#### Editing a user

The edit icon opens a window for ***editing business-related data***. The manager can change the *salary* and, depending on the user type, the *department* (manager) or the *register ID, shift start and shift end* (cashier).

The same rules apply as when adding a user. Fields validate input and saving is disabled until the values are valid. Changes are confirmed with the button or with *Enter*.

#### Changing user type (Manager ↔ Cashier)

The manager can ***change the role*** of a selected user with the corresponding icon. The system asks for confirmation first. If confirmed, the role is updated, and the fields specific to the new role are filled in or reset as needed.

Changing your own role, or the role of an inactive account, is not allowed; in both cases a warning dialog is shown.

#### Activating / deactivating users

The manager can temporarily ***disable*** or re-***enable*** an account without deleting any data. The system asks for confirmation before the status changes.

An inactive user cannot log in and gets a message when trying. While an account is inactive, some manager actions on it are disabled, such as password reset or role change.

Deactivating your own account is not allowed; the attempt shows a dialog stating that the operation is forbidden.

#### Password reset

The manager can ***generate a temporary password*** for a selected user. After a successful reset, a message shows the temporary password, which the manager can pass on to the user.

On the next login the user enters the temporary password and is then required to set a new password of their own.

Resetting your own password, or the password of an inactive account, is not allowed.

### Product management

#### Product list

The manager can browse all products in the shop's assortment. The list shows *ID, name, product type* (*Food, Drink, Utensils*) and *quantity in stock*, with icons for *details*, *editing product data*, *status change* and opening the *stock management* window.

A ***search field*** finds products quickly (*Tab* or *F3* moves focus to it). ***Filtering*** uses a drop-down ***by product type*** (*Ctrl + F*) and an ***Attributes menu*** (*Ctrl + L*), including the options *On sale*, *Featured* and *Available*.

#### Adding a product

The ***Add*** button in the top right corner of the main screen (*Ctrl + N*) opens a form for a new product. The form has basic fields for all products, and additional fields depending on the type (Food, Drink or Utensils).

<p align="center">
  <img src="images/10_menadzer_proizvodi.png" alt="dodaj proizvod" height="250" width="350"/>
</p>

**Common fields**

- *Product type* – drop-down, required: *Food*, *Drink* or *Utensils*,
- *Name* – text field with minimum and maximum length,
- *Description* – multi-line text field,
- *Price* – numeric field; required and not negative,
- *Product image* – photo picker; a preview is shown after selection. Supported formats: *.jpg, .jpeg, .png*.

**Food fields**

- *Food category* – drop-down (*cakes, sweets, pastries, bakery products*),
- *Weight* – numeric field (in grams),
- *Calories* – numeric field that expects an integer,
- *Perishable* – checkbox marking the product as perishable.

**Drink fields**

- *Volume* – numeric field (in millilitres), cannot be negative,
- *Alcoholic* – checkbox indicating whether the product contains alcohol.

**Utensils fields**

- *Material* – required text field (e.g. plastic, metal),
- *Dimensions* – text field in the format "*number*" or "*number × number*"; numbers can be integers or decimals, and spaces are allowed,
- *Reusable* – checkbox indicating whether the item can be reused.

The ***Add*** button validates all visible fields. If the data is valid, the product is saved to the database and a success message is shown. If there are errors, the user gets a warning and the invalid fields are marked. ***Cancel*** closes the form without saving.

#### Product details

<p align="center">
  <img src="images/11_menadzer_proizvodi.png" alt="detalji proizvoda" height="250" width="350"/>
</p>

The details window shows the *name, type, description, price* and *discount*, the *creation* and *last modification dates*, and the *product image*. Chips show the product status: *available, unavailable* or *featured*.

Type-specific attributes depend on the type: for food (*food category, weight, calories, perishable*), for drinks (*volume, alcoholic or non-alcoholic*), for utensils (*material, dimensions, reusable*).

#### Editing basic product data

<p align="center">
  <img src="images/12_menadzer_proizvodi.png" alt="uredi podatke proizvoda" height="250" width="350"/>
</p>

The corresponding icon opens a modal window for editing the ***basic data***. The manager can change the *price*, add or remove a *discount*, and mark the product as *featured*. The fields show the current values.

The same rules apply as when adding a product; saving is disabled until the values are valid (e.g. price and discount must be numeric and not negative). Changes are confirmed with the ***Save*** button or *Enter*, and ***Cancel*** closes the window without changes.

#### Editing product details

<p align="center">
  <img src="images/13_menadzer_proizvodi.png" alt="uredi profil proizvoda" height="250" width="350"/>
</p>

Select a product and click the corresponding icon to ***edit the product profile***. The *name, description, image* and the type-specific attributes can be changed.

The system validates the input and does not allow saving invalid data. Changes are confirmed with the ***Save*** button or *Enter*.

#### Activating / deactivating products

The manager can temporarily ***hide*** or re-***show*** a product in the active list without deleting data. The system asks for confirmation before the status changes.

An inactive product is not shown in the standard view and cannot be added to sales transactions until it is activated again. Some actions, such as editing the price, discount or featured status, are also disabled while the product is inactive.

Deactivating a product that is already inactive is not allowed; a warning dialog is shown.

### Stock management

The icon next to a product opens the ***stock management*** window, where the manager tracks and updates stock. It shows *quantities, supply batches* and *expiry dates*, and critical items are highlighted automatically.

The product name and the *total quantity* currently available are shown at the top. The central area lists all stock batches of the selected product: *batch ID, quantity, date added* and *expiry date*.

Available actions are ***Save*** (confirm changes), ***Discard*** (revert changes) and ***Delete*** (remove the selected item). A ***filter*** control shows batches by status (*active / inactive*).

The right panel shows the ***details*** of the selected item (*quantity, expiry date, warning days, date added*). Fields are validated:

- *Quantity* – required; an integer greater than zero,
- *Expiry date* – optional; if set, must be at least 1 day in the future,
- *Warning days* – optional; a non-negative integer,
- *Date added* – date and time when the item was added,
- *Active* – checkbox to activate or deactivate the item.

Below the panel are the ***Add stock*** button, which creates a new item, and the ***Close*** button, which closes the screen without saving.

If an expiry date exists and the current date is within the number of warning days, the item is automatically shown in a different colour, so the manager can spot critical stock.

The view includes both active and inactive items, whether their status was changed, they expired or they were used up.

### Manager statistics and reports

#### Products

This section shows key business figures in panels and charts.

It has ***From*** and ***To*** date pickers and a ***Statistics*** button that loads data for the chosen period. Both dates are optional: an empty field means no limit on that end; with only *From* set, data from that date onward is shown; with only *To* set, data up to and including that date is shown.

On clicking ***Statistics*** the app first validates the dates. If they are valid, the data is loaded and all panels, charts and the best-sellers list are updated. If the input is invalid (e.g. a future date or an invalid range), the fields are marked with an error and a warning dialog appears; the query does not run until the errors are fixed.

Below the filter bar are these panels:

- ***Orders*** – total number of orders, grouped by status: *Completed, Cancelled* and *Pending*.
- ***Items*** – total number of items, split by category: *Food, Drink* and *Utensils*.
- ***Revenue*** – total revenue in the selected period.

Charts:
- *Line chart* – weekly trend of items sold and number of orders,
- *Bar chart* – revenue trend over the same period.

The screen also has a list of ***best-selling products*** with thumbnails and names, sorted by the number of items sold.

#### Stock

The *Stock* section shows the state of products in the warehouse and all changes made.

The user selects a product, sets a period with the *From* and *To* fields and generates the report with the ***Report*** button. The input is validated: a date cannot be in the future, the end date must be after the start date, and selecting a product is required for detailed reports. Invalid dates or no product selected block report generation, and an error indicator is shown next to the field.

**Tabs:**

- ***Stock*** – items whose expiry date is approaching, regardless of the selected product and period. The table has *stock ID, product ID, product name, quantity, expiry date* and *days until warning*,
- ***Transactions*** – all stock changes for the selected product and period: *transaction ID, date and time, transaction type* (*receipt, sale, correction*), *quantity change, order number* and *user ID*,
- ***Changes*** – all stock changes: *date, change type, previous and new value* and *user ID*,
- ***Summary*** – overall view for the selected product and period: *quantity in stock, quantities added and sold* and *total number of changes*.

Tables support sorting, and empty views tell the user there is no data for the current criteria.

<p align="center">
  <img src="images/15_menadzer_izvjestaji.png" alt="izvjestaj" height="250" width="330"/>
  <img src="images/16_menadzer_izvjestaji.png" alt="izvjestaj" height="250" width="330"/>
</p>

---

## Cashier

The cashier's main responsibilities:
- creating and paying orders,
- tracking and reviewing orders,
- viewing financial and operational reports,
- managing personal settings and profile.

### Login and navigation

After login the ***cashier start screen (POS terminal)*** is shown. The top shows the *profile picture* and *username* of the logged-in cashier.

A vertical ***navigation menu*** is on the left; each item has a keyboard shortcut:

- ***POS (Register)*** – screen for creating and paying orders (*Ctrl + P*),
- ***Orders*** – all transactions and their details (*Ctrl + O*),
- ***Reports*** – financial and operational data for the cashier's work (*Ctrl + R*),
- ***Settings*** – personal account settings, including language and theme (*Ctrl + S*),
- ***Profile*** – edit personal data: username, password, phone number, address and image (*Ctrl + M*),
- ***Logout*** – log out of the application (*Escape*).

The main area shows the ***content of the selected module***.

### POS screen

#### Search

The top of the screen has product filtering and search tools: a drop-down for ***product type*** (food, drink, utensils; *Ctrl + T*), a text field to ***search by product name or type*** (focus with *F3*), and three ***filter toggles***: *Available* (*Ctrl + A*), *Featured* (*Ctrl + F*) and *On sale* (*Ctrl + D*). The options can be combined.

#### Product list

The centre of the screen shows products as scrollable cards. Each card has the *product name, description* (as a tooltip), *price* and a button to ***add to cart*** (***+***). On clicking "***+***" the app checks whether the product is available and in stock, and prevents adding the same product more than once. If the product is unavailable for sale, out of stock or already in the cart, a short notification is shown. When the add succeeds, the cart refreshes immediately.

#### Cart

The cart lists the selected products with *image*, *name* and *price*. *Quantity* is changed with *plus/minus* buttons, and there is a button to *remove a product*. Quantity changes are immediately reflected in the item price and the cart total. Removing a product from the cart also updates the total automatically. Trying to raise the quantity above the available stock shows a short popup saying the stock limit was reached.

#### Total and payment options

<p align="center">
  <img src="images/18_blagajnik_pos.png" alt="blagajnik pos" height="250" width="350"/>
</p>

The ***cart total*** is shown below the product list, with the currency. The cashier has three payment options:

- ***Pay Later*** – payment is deferred (*Ctrl + L*),
- ***Pay Cash*** – payment in cash (*Ctrl + G*),
- ***Pay Card*** – opens a dialog for the card number; after confirmation the card payment is recorded (*Ctrl + N*).

Whichever option is chosen, every transaction creates an order and reduces product quantities in stock; with Pay Cash and Pay Card the payment is recorded too, while with Pay Later it is deferred.

The operation has to be confirmed in a dialog before it runs. If it succeeds, the cart is cleared and a success message is shown. If the cart is empty when payment is attempted, the user gets a notification.

### Orders

<p align="center">
  <img src="images/20_blagajnik_porudzbine.png" alt="blagajnik porudžbine" height="250" width="350"/>
</p>

In the centre of the screen a drop-down ***filters orders*** by status (*All, Completed, Cancelled, Pending*); the shortcut is *Ctrl + T*.

Orders the cashier handled in the last 24 hours are shown in a table with the columns *ID, Date, Total price* and *Status*. The table supports column sorting. If there are no orders, the message "*No data*" is shown instead of the table.

A side panel on the right shows ***order details***: selecting a row loads the order's items (*product name, quantity, unit price* and *item total*) and the order total.

For the selected order the following actions are available:

- ***Cancel*** – cancels an existing order. A confirmation dialog is shown, after which the stock for all items in the order is restored. If the order was pending, its status becomes "*Cancelled*"; if it was already completed, the status becomes "*Refunded*" and a refund is made (the cash balance is reduced). An already cancelled order cannot be cancelled again. Shortcut: *Ctrl + L*.
- ***Pay Cash*** – cash payment applies to orders with the status "*Pending*". A cancelled or already paid order cannot be paid; the app blocks the attempt and shows a dialog. Shortcut: *Ctrl + G*.
- ***Pay Card*** – card payment also applies to "*Pending*" orders. A dialog asks for the card number (required and validated); after confirmation the payment is recorded and the order is updated. As with cash, a cancelled or already paid order cannot be paid. Shortcut: *Ctrl + N*.

If cancelling or paying is attempted with no order selected, a dialog reports an invalid operation. Each successful operation shows an informational message.

### Cashier statistics and reports

The ***Reports*** screen shows key metrics in panels and charts. All views refer to the logged-in cashier (by *user ID*).

- Top: *total number of orders*, *total items sold* and *total revenue* from the logged-in user's work.
- Bottom left: daily statistics – *today's orders* by status (*Completed, Cancelled, Pending*), *daily revenue* and *items sold* by category (*food, drink, utensils*). If there is no data, the message "*No orders*" is shown instead of a chart.
- A *line chart* shows the *weekly number of items* and *orders* for the cashier's work, and a *bar chart* shows the *revenue* trend over the same period.
- A list of *best-selling products*.

<p align="center">
  <img src="images/21_blagajnik_izvjestaji.png" alt="izvjestaj" height="280" width="380"/>
</p>

---

## Shared features

These are available to both the manager and the cashier: ***language*** and ***theme settings***, and ***profile editing***.

### Settings (language and theme)

The user can set the theme and language of the interface:

- ***Themes*** – ***light***, ***dark*** and ***blue***,
- ***Languages*** – ***Serbian*** and ***English*** are currently supported.

The language and theme drop-downs have an icon next to each option, and the labels follow the currently active language.

Clicking ***Save*** compares the selected language and theme with the previous values and applies any changes immediately. You can change only the theme, only the language, or both.

<p align="center">
  <img src="images/22_zajednicke_teme.png" alt="teme" height="250" width="330"/>
  <img src="images/29_zajednicke_jezik.png" alt="jezik" height="250" width="330"/>
</p>

The user gets a message with the result ("*Theme and language changed*", "*Theme changed*", "*Language changed*" or "*No changes*"). The chosen settings are stored for that user, so the previously selected options are available at every later login.

*Examples of different themes:*

<p align="center">
  <img src="images/23_zajednicke_teme.png" alt="teme" height="250" width="330"/>
  <img src="images/26_zajednicke_teme.png" alt="teme" height="250" width="330"/>
</p>
<p align="center">
  <img src="images/24_zajednicke_teme.png" alt="teme" height="250" width="330"/>
  <img src="images/27_zajednicke_teme.png" alt="teme" height="250" width="330"/>
</p>
<p align="center">
  <img src="images/25_zajednicke_teme.png" alt="teme" height="250" width="330"/>
  <img src="images/28_zajednicke_teme.png" alt="teme" height="250" width="330"/>
</p>

*Example of changing the language:*

<p align="center">
  <img src="images/30_zajednicke_jezik.png" alt="jezik" height="250" width="330"/>
  <img src="images/31_zajednicke_jezik.png" alt="jezik" height="250" width="330"/>
</p>

### User profile

When the ***User profile*** page opens, the current data is already loaded, so it can be reviewed and edited.

<p align="center">
  <img src="images/32_zajednicke_profil.png" alt="profil korisnika" height="250" width="350"/>
</p>

The user can change:

- ***Username*** – required; letters and digits only, with a length limit, and must be unique,
- ***Password*** – optional; if entered, the same rules as for the username apply. The field is masked,
- ***Phone number*** – required; must match a phone number format,
- ***Address*** – no additional constraints,
- ***Choose image*** – opens a picker; supported formats are *jpg, jpeg* and *png*.

Buttons:

- ***Save*** – validates the input and, if valid, saves the changes to the profile (*Ctrl + S*),
- ***Reset*** – restores the previously active values, discarding recent edits (*Ctrl + R*).

### Adaptive layout

The interface layout adapts to the screen size on desktop and laptop computers. On larger screens, product lists and navigation icons are arranged in several columns, and on smaller screens the layout switches to fewer columns automatically. At smaller widths some images may be hidden to save space.

*Example of the layout adapting:*

<p align="center">
  <img src="images/33_zajednicke_responzivnost.png" alt="responzivnost" height="250" width="330"/>
  <img src="images/34_zajednicke_responzivnost.png" alt="responzivnost" height="250" width="250"/>
</p>
<p align="center">
  <img src="images/35_zajednicke_responzivnost.png" alt="responzivnost" height="250" width="330"/>
  <img src="images/36_zajednicke_responzivnost.png" alt="responzivnost" height="250" width="250"/>
</p>
