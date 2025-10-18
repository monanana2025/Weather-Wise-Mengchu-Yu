# Intentional Prompting Journey – WeatherWise Project
**Project:** WeatherWise – AI-enhanced Weather Application  

This document records how I worked with ChatGPT and Colab AI to design, debug, and improve my WeatherWise project.  
Each part describes one prompting theme, including the problem I faced, the question I asked, the AI suggestion, and what I learned from it.  
The purpose of this journal is to show how AI-supported learning helped me think logically and build a better solution.

---

## Part 1: Input Optimisation
**Goal:** Make user input simpler and prevent invalid entries.  

At the beginning, I allowed users to type any city name. However, I often received errors because the text did not match API input rules.  
I asked AI:  
> “Should I use dropdown menus instead of free typing for city input?”  

**AI Suggestion:**  
AI explained that dropdown menus or predefined options help control input, reduce validation work, and improve user experience. It also suggested using `ipywidgets.Dropdown` for a cleaner interface.  

**Impact:**  
I redesigned the UI with dropdowns for city and forecast days. The interface became smoother, and users could not make typing mistakes.  
I also learned that reducing user freedom in input can improve both accuracy and performance.

---

## Part 2: Modular Design
**Goal:** Separate data functions and UI logic to improve structure.  

In my first version, I wrote UI widgets and data retrieval in the same cell. This made debugging difficult.  
I asked AI:  
> “Can I put date selection inside the data retrieval function?”  

**AI Suggestion:**  
AI advised me to follow modular design—each part should have a single responsibility. Data functions should only get and process weather data, while UI functions should handle interaction.  

**Impact:**  
I reorganised my notebook into clear sections: *Data Retrieval*, *NLP Analysis*, *Visualisation*, and *UI*.  
This helped me understand how modular programming improves readability and maintenance.  
Later, I used this same structure to design other small apps.

---

## Part 3: API Error 405
**Goal:** Understand and fix the 405 “Method Not Allowed” error.  

When I tested the weather API, I kept getting a 405 error and thought my API key was invalid.  
I asked AI:  
> “My weather API gives 405. Is my key wrong?”  

**AI Suggestion:**  
AI explained that 405 means I used the wrong HTTP method — probably `POST` instead of `GET`.  
It also showed how to print status codes to check responses quickly.  

**Impact:**  
I fixed the request method and added a small error-checking block.  
From this, I learned how to read HTTP error codes, test endpoints safely, and avoid guessing during debugging.

---

## Part 4: Colab–GitHub Saving Issue
**Goal:** Solve saving and syncing issues between Colab and GitHub.  

When I tried to push my notebook to GitHub after running interactive cells, the system failed to save.  
I asked AI:  
> “Why can’t I save my notebook to GitHub after running the UI section?”  

**AI Suggestion:**  
AI said that interactive widgets can block the saving process because they store temporary outputs.  
It recommended restarting the runtime or clearing outputs before syncing.  

**Impact:**  
After restarting Colab and removing the widgets, I could save normally.  
This experience helped me understand how Colab manages sessions and how to safely push updates to GitHub.  
It also reminded me to always test saving early before long interactive work.

---

## Part 5: Testing Without API Key
**Goal:** Submit the project securely without losing functionality.  

Before submission, I worried that removing my API key would break the program.  
I asked AI:  
> “If I remove my API key before upload, will my project still work?”  

**AI Suggestion:**  
AI explained that for grading, mock APIs are usually used, so my code would still be testable if the function names stayed the same.  
It suggested keeping the environment variable `os.getenv("OPENWEATHER_API_KEY")` but not uploading the actual key.  

**Impact:**  
I followed this method and confirmed that my notebook still ran properly.  
This made me more confident about balancing **security** and **functionality** in data projects.

---

## Part 6: Colab AI Code Optimisation
**Goal:** Improve performance and learn clean coding habits.  

While testing loops, I asked Colab AI:  
> “Is list comprehension faster than a for-loop?”  

**AI Suggestion:**  
Colab AI explained that list comprehensions run faster because they use internal optimisation and fewer variable assignments.  
It also showed me how to test runtime with `timeit`.  

**Impact:**  
I replaced several for-loops with list comprehensions and confirmed shorter execution time.  
This part taught me not only how to optimise code but also how to measure performance objectively instead of guessing.

---

## Part 7: Visualisation Design
**Goal:** Make graphs easier to understand and visually consistent.  

My early visualisations were messy and lacked labels.  
I asked AI:  
> “How can I make my temperature graph easier to read?”  

**AI Suggestion:**  
AI recommended adding a title, x/y-axis labels, legends, and adjusting the figure size for better spacing.  
It also explained how to use consistent colours for each data line.  

**Impact:**  
The updated charts looked more professional and were easier for users to read.  
This step improved my awareness of user experience and presentation aesthetics, which are important even in data-driven apps.

---

## Part 8: Error Handling
**Goal:** Stop the notebook from crashing when input is invalid.  

Sometimes users entered empty or misspelled city names, and the code stopped running.  
I asked AI:  
> “How can I prevent my notebook from crashing when input is wrong?”  

**AI Suggestion:**  
AI showed me how to wrap the API request in a `try/except` block and return a clear message when an error occurs.  
It also suggested adding a default value to keep the program running.  

**Impact:**  
After implementing error handling, the notebook stayed stable and user-friendly.  
This made me realise that small defensive coding habits can greatly improve program reliability.

---

## Overall Reflection
Through these eight parts, I learned how to communicate with AI clearly and apply its advice critically.  
Every prompt became a small learning activity — from debugging to improving user experience.  
AI helped me understand programming principles like modularity, efficiency, and usability more deeply.  
Most importantly, I discovered that **AI is not a shortcut**, but a partner that makes my own learning more structured and reflective.
