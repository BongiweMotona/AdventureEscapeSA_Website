# Adventure Escape SA — Website

## 1. Project Overview

Adventure Escape SA is an outdoor adventure and eco-tourism company based in the Western Cape, South Africa. The website provides visitors with information about the company, its adventure packages and individual activities, group booking fees, and contact details.

The website was developed using HTML, CSS, and JavaScript without external frameworks or a separate build process. Visual Studio Code was used for development, and the website was previewed locally using the Live Server extension (Dey, n.d.).

## 2. Client Requirements

The website is designed to meet the following requirements:

* Introduce Adventure Escape SA and its services.
* Present the company's background and core values.
* Display available adventure packages and individual activities.
* Provide detailed information about selected packages and activities.
* Allow visitors to calculate estimated group booking fees and applicable discounts.
* Provide a contact form for visitor enquiries.
* Maintain consistent navigation, styling, and functionality across the website.

## 3. Website Pages and Functionality

The website consists of six pages.

### 3.1 Home

The Home page introduces Adventure Escape SA through a hero banner and showcases featured adventure packages. It provides visitors with an entry point to explore the company's offerings.

### 3.2 About Us

The About Us page presents the company's background and its three core values:

* **Teamwork** — supporting local guides, operators, and small businesses.
* **Fitness** — providing real, guided outdoor experiences for visitors of every skill level.
* **Love of Nature** — operating responsibly in the natural spaces the company relies on.

### 3.3 Overview

The Overview page allows visitors to switch between Packages and Activities. Both categories are presented using a card-based layout to make the available experiences easier to browse.

### 3.4 Individual

The Individual page displays detailed information about a selected package or activity, including its description, pricing, and inclusions.

### 3.5 Calculate Fee

The Calculate Fee page provides an interactive quotation tool for group bookings. Visitors can adjust quantities and view the calculated discount and total update dynamically using JavaScript.

### 3.6 Contact Us

The Contact Us page provides a form for visitor enquiries. Client-side form validation helps identify invalid or incomplete entries in the browser before submission (Mozilla Developer Network, n.d.-b).

The contact form requires a suitable submission service or backend integration if enquiries are to be delivered directly to the company.

## 4. Design and User Interface

### 4.1 Colour Palette

The website uses a visual identity called **Bushveld Blaze**, inspired by outdoor adventure and the natural environment.

| Colour       | Hex Code  | Purpose                  |
| ------------ | --------- | ------------------------ |
| Forest green | `#19472A` | Primary brand colour     |
| Amber        | `#D6810B` | Calls to action          |
| Coral        | `#FF7F6B` | Secondary accent         |
| White        | `#FFFFFF` | Backgrounds and surfaces |
| Charcoal     | `#333333` | Body text and contrast   |

Forest green establishes the primary brand identity, while amber highlights important actions. Coral provides a secondary accent, and white and charcoal support readability and visual contrast.

### 4.2 Images and Layout

The website currently uses grey placeholder boxes to represent photography. These placeholders allow the page layouts to be developed before the final images are selected.

When actual images are added, the CSS `object-fit` property can be used to control how images fit within their containers, helping maintain the intended layout and image proportions (Mozilla Developer Network, n.d.-a).

### 4.3 Consistent Navigation and Styling

A shared stylesheet and JavaScript file support consistent styling and functionality across the six pages.

Shared functionality includes navigation, tab behaviour, fee calculations, and client-side form validation.

## 5. Technologies and Tools

| Technology or Tool | Purpose                                                                                      |
| ------------------ | -------------------------------------------------------------------------------------------- |
| HTML               | Structures the website content.                                                              |
| CSS                | Controls the layout, styling, colours, and presentation.                                     |
| JavaScript         | Implements interactive features, fee calculations, tab behaviour, and form validation.       |
| Visual Studio Code | Used to develop and edit the website.                                                        |
| Live Server        | Used to preview the website locally during development.                                      |
| GitHub             | Used to store and manage the project repository, track changes, and support version control. |

The website does not require a separate framework installation or build process.

## 6. Running the Website

The website can be previewed locally using Visual Studio Code and the Live Server extension.

1. Open the website project folder in Visual Studio Code.
2. Ensure the HTML, CSS, and JavaScript files are available in the project.
3. Open the website's entry HTML file.
4. Right-click the file and select **Open with Live Server**.
5. View the website in the browser.

The exact entry HTML filename depends on the project's file structure.

## 7. Current Limitations and Future Improvements

The following items from the earlier version of this list were completed in Task 3 (see Section 9, Changelog):

* **Package catalogue and pricing:** all four packages and three activities are listed with their final prices.
* **Group booking discounts:** the discount tiers are confirmed (5%, 10% and 15% for more than three bookings) and shown in a table on the Calculate Fee page.
* **Photography:** the grey placeholder boxes have been replaced with adventure photographs.

The following items remain to be addressed as the website develops:

* **Contact form integration:** connect the form to a service or backend so enquiries are delivered directly to the company. The form currently validates the input but does not send it anywhere.
* **Saving a quotation:** items added on the Calculate Fee page are cleared when the visitor leaves the page. Storing them in the browser would let a quotation be kept while the visitor moves between pages.
* **Contact details and map:** replace the placeholder phone number with the company's number, and replace the static map image with an interactive map.
* **Testing:** continue testing the pages, navigation, fee calculations and form validation on more browsers and devices.

## 8. Team Members

1. Kabelo Litheko — ST10517750
2. Bongiwe Motona — ST10520889
3. Thando Shongwe — ST10539919
4. Thandazile Xaba — ST10515020

## 9. Changelog

### Task 3 (November 2026)

**Publishing and images**

* Moved the website into the `docs` folder so it can be published with GitHub Pages.
* Replaced the remaining image placeholders with activity photographs, linked to each package and activity.

**Calculate Fee page**

* Added a **Group discounts table**, built from the `DISCOUNT_TIERS` array, that highlights the tier the customer currently qualifies for.
* Added an **itemised quotation table** (item, number of people and amount) to the Quotation Summary.
* Each different package or activity now counts as one booking, matching the mobile application. The number of people multiplies the price but does not count as extra bookings.
* Amounts are shown to the cent (for example R4 096.88), with the discount and VAT rounded to the cent.
* Added validation that limits each booking to 20 people and shows an error message if more are added.

**Contact Us page**

* Added a **drop-down menu** for the package or activity of interest. Its options are built from the `CALC_DATA` array and grouped into packages and activities.
* The drop-down is validated like the other fields and is pre-selected when the visitor arrives from the Calculate Fee page.

**Navigation, design and fixes**

* The **Book Now** button now opens the Calculate Fee page and uses white text for readability.
* The **Activities** menu link now opens the Individual Activities tab, and Calculate Fees was added to the footer links.
* Replaced the "ICON" placeholders on the About Us page with icons.
* Improved the logo's alternative text, defined the missing focus-outline colour, and corrected spelling errors.

## 10. References

Dey, R. (n.d.) *Live Server*. Visual Studio Code Marketplace. Available at: https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer (Accessed: 7 October 2026).

Mozilla Developer Network (n.d.-a) *object-fit*. MDN Web Docs. Available at: https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit (Accessed: 7 October 2026).

Mozilla Developer Network (n.d.-b) *Client-side form validation*. MDN Web Docs. Available at: https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation (Accessed: 7 October 2026).
