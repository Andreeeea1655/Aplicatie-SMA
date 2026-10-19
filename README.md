# BookRecomandations

An Android app that recommends books based on the **tropes** you want (and the ones you want to avoid), instead of relying on ratings or broad genres.

Most book apps make you pick a genre and then scroll through rating-sorted lists. But “fantasy” can mean anything from cozy to grimdark. When you want something more specific, you just pick the tropes/attributes you’re in the mood for, cross out the ones you don't want, and the app shows you the books that match the most.

---

## Features

- Browse a local catalog of books, each labeled with tropes
- Select tropes to **include** and to **exclude** using filter chips
- Results ranked by how many of the selected tropes a book matches (e.g. "4/5 matches")
- Book details screen (title, author, description, all tropes)
- Works fully offline: the catalog is stored locally


## How the recommendation works

Every book has a set of tropes/attributes assigned from a **fixed vocabulary** (a controlled list of tags, for example `political intrigue`, `vampire`, `classic`, `love triangle`,  `enemies to lovers`).

When the user searches:

1. **Exclude filter:** any book that has at least one excluded trope is removed.
2. **Scoring:** each remaining book gets a score equal to the number of selected (included) tropes it has.
3. **Ranking:** books are sorted by score in descending order, and the result shows the match ratio (matched / selected).

Example: searching for `classic` + `regency era` + `enemies to lovers` and excluding `gothic` keeps only books without a gpthic setting and puts the ones matching all three included tropes at the top, like Pride and Prejudice by Jane Austen.

---

## Tech stack

- **Language:** Kotlin
- **UI:** Jetpack Compose
- **Architecture:** MVVM (ViewModel + StateFlow)
- **Local database:** Room (SQLite)
- **Navigation:** Navigation Compose
- **IDE:** Android Studio
  
---

## Roadmap

- [ ] Define the trope vocabulary
- [ ] Label an initial catalog of books (30 to 50)
- [ ] Room database and repository
- [ ] Search screen with include/exclude chips
- [ ] Ranked results and details screens
