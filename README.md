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

The following items remain to be addressed as the website develops:

* **Package catalogue and pricing:** Finalise the adventure package information and pricing.
* **Group booking discounts:** Expand and confirm the discount tiers for larger bookings.
* **Contact form integration:** Connect the form to a service or backend so enquiries can be delivered directly to the company.
* **Photography:** Replace the grey placeholder boxes with suitable adventure and tourism photographs.
* **Testing:** Continue testing the pages, navigation, fee calculations, and form validation to identify and correct issues.

These improvements will help bring the website closer to its intended functionality and presentation.

## 8. Team Members

1. Kabelo Litheko — ST10517750
2. Bongiwe Motion — ST10520889
3. Thando Shongwe — ST10539919
4. Thandazile Xaba — ST10515020

## 9. References

Dey, R. (n.d.) *Live Server*. Visual Studio Code Marketplace. Available at: https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer (Accessed: 7 October 2026).

Mozilla Developer Network (n.d.-a) *object-fit*. MDN Web Docs. Available at: https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit (Accessed: 7 October 2026).

Mozilla Developer Network (n.d.-b) *Client-side form validation*. MDN Web Docs. Available at: https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation (Accessed: 7 October 2026).
