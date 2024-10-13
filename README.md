Overview

This project is a simple Stock Price Tracker web application that allows users to track stock prices for multiple companies. The app dynamically fetches stock prices using the Yahoo Finance API via Flask and displays them on the frontend using jQuery for live updates. Users can add or remove stock tickers and the page will periodically refresh the stock prices and display changes.
Features

    Add stock tickers to track and store them locally in the browser.
    Remove stock tickers from the grid.
    Stock prices automatically update every 15 seconds.
    Stock price changes are color-coded to visually indicate price movements:
        Dark Red: Price dropped significantly (>= 2%)
        Red: Price dropped
        Gray: No price change
        Green: Price increased slightly (<= 2%)
        Dark Green: Price increased significantly (> 2%)
    Flash effect to indicate whether a stock price has increased or decreased in the latest update.

How it Works

    Frontend:
        Uses HTML, CSS, and JavaScript (with jQuery) to handle user interactions and dynamically update the stock ticker grid.
        Ticker symbols are stored in the browser's localStorage, so they persist between sessions.
        A countdown timer shows the time remaining before the next price update.
        When a new ticker is added, it fetches stock data and updates the UI with current price and percentage change.
        Clicking the "Remove" button next to a ticker removes it from the list.

    Backend:
        The backend is built using Flask in Python.
        The /get_stock_data route retrieves stock data from Yahoo Finance via the yfinance Python library.
        The server returns the current price and open price for the requested ticker.

Setup Instructions
Prerequisites

    Python 3.x
    Flask
    yfinance (pip install yfinance)
    jQuery (included via CDN in the HTML file)

Functionality Breakdown
Frontend:

    startUpdateCycle(): Initiates a 15-second countdown that triggers a price update when the timer reaches zero.
    addTickerToGrid(ticker): Adds a stock ticker to the grid for tracking.
    updatePrices(): Fetches current stock price and percentage change for each ticker using AJAX and updates the UI accordingly.
    removeTicker(): Removes a ticker from the grid and localStorage when the remove button is clicked.

Backend:

    /get_stock_data: Receives a POST request with a stock ticker symbol, fetches the stock's latest price and opening price using the yfinance library, and returns the data as JSON.

Future Improvements

    Display historical stock data (e.g., weekly or monthly changes).
    Add real-time streaming for price updates.
    Support for multiple stock exchanges.
