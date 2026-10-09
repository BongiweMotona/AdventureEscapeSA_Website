# Adventure Escape SA – Website

Student project: website component
Module: [module name and code] · Institution: [institution] · Lecturer: [lecturer name]
Group members: [Name Surname – student number], [Name Surname – student number], [Name Surname – student number]
Submission date: [date]

---

## 1. Project overview

Adventure Escape SA is a small-to-medium enterprise (SME) founded by Liam Daniels in 2024. It offers professionally guided outdoor experiences throughout the Western Cape. According to the client brief, families, tourists, schools and corporate groups struggle to find one place where they can compare and book outdoor activities.

This website meets that need. It lets customers:

- browse the company's Adventure Packages and Individual Activities,
- view the details of each experience (description, what is included and price),
- build a quotation for one or more bookings, with the group discount and VAT calculated automatically, and
- send an enquiry to the company through a contact form.

The site was developed from the Phase 3 wireframes and has the six required pages:

| # | Page | File | Purpose |
|---|---|---|---|
| 1 | Home | `index.html` | Branding, hero section and popular Adventure Packages |
| 2 | About Us | `about.html` | The company's story and what it stands for |
| 3 | Overview | `overview.html` | Tabbed list of all Adventure Packages and Individual Activities |
| 4 | Individual page | `individual.html` | Details of one experience, loaded by URL (e.g. `individual.html?item=ziplining`), with "You May Also Like" suggestions |
| 5 | Calculate Fee | `calculate.html` | The customer's bookings, quantity controls, discount progress and quotation total |
| 6 | Contact Us | `contact.html` | Validated enquiry form and contact details |

---

## 2. Client brief requirements and how the site meets them

### 2.1 Catalogue

| Type | Experience | Fee | Includes (from brief) |
|---|---|---|---|
| Package | Ultimate Adventure Day | R1 500 | Guided hiking trail, ziplining, kayaking, lunch, safety briefing and equipment |
| Package | Family Explorer Package | R1 500 | Nature walk, obstacle course, picnic area, family games, guided wildlife spotting |
| Package | Mountain Adventure Package | R1 500 | Mountain hiking, scenic viewpoints, rock scrambling, safety equipment, professional guide |
| Package | Corporate Team Challenge | R1 500 | Team obstacle course, orienteering challenge, raft-building activity, leadership exercises, team awards |
| Activity | Ziplining Adventure | R750 | Safety briefing, equipment hire, professional instructors |
| Activity | Kayaking Experience | R750 | Kayak and paddle, safety equipment, guided route |
| Activity | Rock Climbing Session | R750 | Climbing equipment, safety instruction, professional guide |

Item details are stored in the `ITEM_DETAILS` object in `js/script.js`, and prices for the calculator are stored in the `CALC_DATA` array in the same file.

### 2.2 Discount and VAT rules

| Number of bookings | Discount |
|---|---|
| 1 | None |
| 2 | 5% |
| 3 | 10% |
| More than 3 | 15% |

Design decision: each unit of an item in the quotation counts as one booking. The − / + controls on the Calculate page change the quantity of an item, so adding a second unit of the same item also counts towards the discount tier.

VAT of 15% is applied to the amount **after** the discount. The order is: subtotal → discount → VAT → total.

Example: Ultimate Adventure Day (R1 500) plus Kayaking Experience (R750) = 2 bookings. Subtotal R2 250, 5% discount R112.50, amount after discount R2 137.50, VAT R320.63, total about R2 458 (shown to the nearest rand). This is a quotation only, not a formal invoice.

This logic is in `updateSummary()` in `js/script.js`, using the `DISCOUNT_TIERS` array and the `VAT_RATE` constant.

---

## 3. Design

### 3.1 User-centred design

The site follows a user-centred design (UCD) approach. The needs, tasks and context of the intended users, mainly families and tourists, drive design decisions throughout development (ISO, 2019; Norman, 2013). In practice this meant:

- **Clear navigation:** the same five items (Home, Packages, Activities, About, Contact) appear on every page, with a visible "Book Now" button. Research suggests that navigation with only a few top-level choices performs best when it is visible rather than hidden (Pernice and Budiu, 2016). On small screens the menu collapses behind a toggle button.
- **Clear homepage:** the Home page states what the business offers and links straight to the packages (Wang, 2024).
- **Responsive layout:** pages adapt to phone, tablet and desktop screen sizes (Nielsen Norman Group, 2020).
- **Immediate feedback:** the quotation total, discount and VAT update as soon as a quantity changes (Norman, 2013).
- **Error prevention:** the contact form checks for an empty name, an invalid email address and an empty message before it accepts the form (Nielsen, 1994).

### 3.2 Colour palette

| Colour | Hex | Use on the site |
|---|---|---|
| Adventure Green | `#24B358` | Primary colour: header, footer, key surfaces |
| Sunset Orange | `#E8743B` | Secondary colour: buttons and calls to action |
| Coral | `#FF7F6B` | Accent colour: sparing highlights |
| Charcoal | `#333333` | Main body text |
| White | `#FFFFFF` | Backgrounds |

All colours are defined as CSS custom properties in the `:root` block at the top of `css/style.css` (MDN Web Docs, n.d.-a), so the whole site can be re-themed from one place.

### 3.3 Logo

The logo shows a diamond with a mountain range, forest and a rising sun, above the words ADVENTURE ESCAPE SA. The site currently shows a "LOGO" placeholder in the header until the logo file is added.

---

## 4. Technical infrastructure

| Item | Detail |
|---|---|
| Editor | Visual Studio Code with the Live Server extension |
| Markup | HTML5 |
| Styling | CSS3 with custom properties and a responsive layout (no framework) |
| Scripting | Vanilla JavaScript in `js/script.js` (no libraries, no build step) |
| Design tool | Figma (low-fidelity wireframes) |
| Version control | [e.g. GitHub repository link] |
| Collaboration | WhatsApp, Microsoft Teams, Microsoft SharePoint |

### 4.1 Architecture

The site is a static multi-page website. Every page loads the same stylesheet (`css/style.css`) and the same script (`js/script.js`). Each part of the script only runs if the elements it needs exist on the current page:

```
js/script.js
 ├── initNavToggle()        every page      mobile menu toggle
 ├── initTabs()             overview.html   Packages / Activities tabs
 ├── initIndividualPage()   individual.html reads ?item= and fills in the details
 ├── initCalculator()       calculate.html  quantities, discount, VAT, suggestions
 └── initContactForm()      contact.html    form validation
```

Other technical choices:

- **One page for all experiences:** `individual.html` reads the `?item=` value from the address bar with `URLSearchParams` (MDN Web Docs, n.d.-b) and looks it up in `ITEM_DETAILS`, so one file serves all seven packages and activities.
- **"Add to Booking" flow:** the button links to `calculate.html?item=…`, and the calculator automatically adds that item with a quantity of 1.
- **"You May Also Like":** shown on the individual page (three other items) and the Calculate page (items not yet in the quotation, each with an Add button).
- **Booking state:** the quotation is held in memory in the `CALC_DATA` array and is reset when the page is reloaded.

---

## 5. Project structure

```
website_project/
├── index.html          Home
├── about.html          About Us
├── overview.html       Overview (tabs)
├── individual.html     Individual page (dynamic)
├── calculate.html      Calculate Fee
├── contact.html        Contact Us
├── README.md
├── css/
│   └── style.css       All styling and the colour variables
└── js/
    └── script.js       All behaviour (see section 4.1)
```

### 5.1 Where to change content

| What | Where | How |
|---|---|---|
| Brand colours | `css/style.css` | Edit the variables in the `:root` block |
| Item descriptions and "Includes" lists | `js/script.js` | Edit the `ITEM_DETAILS` object |
| Prices | `js/script.js` and the cards in `index.html` / `overview.html` | Update `ITEM_DETAILS`, `CALC_DATA` and the price text on each card |
| Discount tiers and VAT | `js/script.js` | Edit `DISCOUNT_TIERS` and `VAT_RATE` |
| Images | Each page | Replace the `.placeholder` boxes with `<img>` tags |

---

## 6. How to run the site

1. Open the project folder in Visual Studio Code with **File → Open Folder**.
2. Install the **Live Server** extension if it is not already installed.
3. Right-click `index.html` and choose **Open with Live Server**.
4. The site opens in the browser and refreshes each time a file is saved.

The site can also be opened by double-clicking `index.html`. No installation or build step is needed.

---

## 7. Testing

### 7.1 Manual test checklist

| # | Test | Expected result | Pass? |
|---|---|---|---|
| 1 | Click each item in the navigation bar | The correct page opens | |
| 2 | Resize the browser to phone width | The menu collapses behind the toggle button | |
| 3 | Overview: switch between the two tabs | The list shows 4 packages or 3 activities | |
| 4 | Click a card on Home or Overview | The individual page shows that item's name, price and includes list | |
| 5 | Click Add to Booking on an item page | Calculate opens with that item already in the quotation | |
| 6 | Add 2 bookings in total | Discount shows 5% | |
| 7 | Add a 3rd booking, then a 4th | Discount shows 10%, then 15% | |
| 8 | Check the totals | VAT is 15% of the amount after discount | |
| 9 | Press − at quantity 1, or press Remove | The item is removed from the quotation | |
| 10 | Click Add on a "You May Also Like" card (Calculate) | The item is added and leaves the suggestions | |
| 11 | Submit the contact form empty or with a bad email | Error messages appear under the fields | |
| 12 | Submit the contact form correctly | A confirmation message appears and the fields clear | |

---

## 8. Known limitations and future work

- The quotation is stored in memory only and is cleared when the page is reloaded.
- The contact form does not send a real email or store the request. It shows a confirmation only.
- The Calculate page does not yet include fields for the customer's name, phone number and email address.
- The About Us page does not yet include separate History, Vision, Mission and Goals sections.
- The Contact page does not yet include social media links, physical venue addresses or a map for directions, and the phone number and email address are fictional.
- The site does not yet include a drop-down menu or a table, which the project brief lists as additional requirements.
- Images and the logo are placeholders until final files are supplied (see section 5.1).

---

## 9. Change log

No entries yet.

---

## 10. Declaration of AI use

Generative AI (Claude, Anthropic, 2026) was used during development to help update the package names and colour variables to match the client brief, build the dynamic individual page, add the discount and VAT calculation, add the "You May Also Like" sections, and draft this README. All AI output was reviewed, tested and adjusted by the group, which takes full responsibility for the submitted work.

---

## 11. References

Anthropic. (2026) Claude [Large language model]. Available at: https://claude.ai (Accessed: 9 October 2026).

ISO. (2019) ISO 9241-210:2019 Ergonomics of human-system interaction – Part 210: Human-centred design for interactive systems. Geneva: International Organization for Standardization.

MDN Web Docs. (n.d.-a) Using CSS custom properties (variables). Available at: https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties (Accessed: 9 October 2026).

MDN Web Docs. (n.d.-b) URLSearchParams. Available at: https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams (Accessed: 9 October 2026).

Nielsen, J. (1994) 10 usability heuristics for user interface design. Nielsen Norman Group. Available at: https://www.nngroup.com/articles/ten-usability-heuristics/ (Accessed: 9 October 2026).

Nielsen Norman Group. (2020) Responsive web design (RWD) and user experience. Available at: https://www.nngroup.com/articles/responsive-web-design-definition/ (Accessed: 9 October 2026).

Norman, D. (2013) The Design of Everyday Things. Revised and expanded edn. New York: Basic Books.

Pernice, K. and Budiu, R. (2016) How to make navigation (even a hamburger) discoverable on mobile. Nielsen Norman Group. Available at: https://www.nngroup.com/articles/find-navigation-mobile-even-hamburger/ (Accessed: 9 October 2026).

Wang, H. (2024) Homepage design: 5 fundamental principles. Nielsen Norman Group. Available at: https://www.nngroup.com/articles/homepage-design-principles/ (Accessed: 9 October 2026).
