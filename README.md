# Conference Expense Planner

A dynamic application designed to simplify the planning and calculation of conference expenses. This project leverages React components, Redux Toolkit, and modern JavaScript to manage states and display cost details in real time. 

## Features

- **Dynamic Component Structure**: Utilized React function components for modular design.
- **State Management**: Implemented Redux Toolkit slices to manage application states efficiently.
- **Dynamic Updates**: Created actions and reducers to increment, decrement, and manage item quantities.
- **Cost Calculation**: Displayed costs using JavaScript arrays and the `map()` function for dynamic content rendering.
- **Interactive Table**: Developed a table to display selected products with detailed breakdowns (names, unit costs, quantities, subtotals).
- **Scalable Design**: Ready to evolve into a fully functional shopping cart application.

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/en/) (version 14 or higher)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/conference-expense-planner.git
   ```
2. Navigate to the project directory:
   ```bash
   cd conference-expense-planner
   ```
3. Install dependencies:
   ```bash
   npm install
   ```

4. Start the development server:
   ```bash
   npm start
   ```

---

## Project Overview

### Application Structure

- **Components**:
  - `ConferenceEvent.jsx`: The main component handling the UI and interactions.
  - `ItemsDisplay`: A sub-component responsible for rendering the selected items and their details.
- **Slices**:
  - `avSlice.jsx`: Manages AV equipment states (e.g., Projectors, Speakers).
  - `mealsSlice.jsx` & `venueSlice.jsx`: Manage meal and venue states respectively.

### State Management

Utilized Redux Toolkit to create and manage slices. Example:

#### `avSlice.jsx`
```javascript
import { createSlice } from "@reduxjs/toolkit";

export const avSlice = createSlice({
  name: "av",
  initialState: [
    { name: "Projectors", cost: 200, quantity: 0 },
    { name: "Speakers", cost: 35, quantity: 0 },
    ...
  ],
  reducers: {
    incrementAvQuantity: (state, action) => {
      const item = state[action.payload];
      if (item) item.quantity++;
    },
    decrementAvQuantity: (state, action) => {
      const item = state[action.payload];
      if (item && item.quantity > 0) item.quantity--;
    },
  },
});

export const { incrementAvQuantity, decrementAvQuantity } = avSlice.actions;
export default avSlice.reducer;
```

### Dynamic Cost Calculation

The application dynamically calculates and displays costs for venues, AV equipment, and meals using array iteration and Redux state updates.

---

## Future Development

- Expand the application into a full-fledged shopping cart.
- Add authentication for user-specific cart management.
- Integrate with a backend service for data persistence.

---

## Usage

1. Start the application by running `npm start`.
2. Use the navigation bar to select categories (Venues, Add-ons, Meals).
3. Add or remove items and view real-time cost updates in the table.

---

## Technologies Used

- **React.js**: For building user interfaces.
- **Redux Toolkit**: For state management.
- **CSS**: For styling the components.

---

## Contributions

Contributions are welcome! Feel free to fork the repository and submit pull requests.

---

## License

This project is licensed under the MIT License.
```

Make sure to replace `https://github.com/yourusername/conference-expense-planner.git` with the actual URL of your GitHub repository.
