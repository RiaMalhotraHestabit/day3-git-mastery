# Merge Postmortem

## Merge Explanation

During Day 3 of the Git Mastery exercise, a merge was performed using two separate local clones of the same GitHub repository.

Both clones modified the same file (`app.js`) and specifically edited the same function (`add`). Each clone introduced its own change and comment. When the changes from one clone were pushed and the other clone attempted to pull the latest updates, Git detected that the same lines of code had been modified in parallel.

Because Git could not automatically determine which version of the code should be kept, it stopped the merge process and reported a merge conflict.

This situation simulates a real-world collaboration scenario where multiple developers work on the same codebase at the same time.

---

## Conflict Resolution

The merge conflict was resolved manually by following these steps:

1. The conflicted file (`app.js`) was opened in a text editor.
   **screenshot**
   
2. Git conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`) were identified in the file.
4. Both changes from Clone 1 and Clone 2 were reviewed carefully.
   
6. Instead of discarding one change, **both comments were preserved** to ensure no contributor’s work was lost.
7. The buggy logic was removed, and the correct numeric addition logic was retained.
8. All conflict markers were removed to restore valid JavaScript syntax.
9. The resolved file was staged and committed, creating a merge commit.

This approach ensured that:
- Both contributors’ changes were kept
- The application logic remained correct
- Git history accurately reflected the merge

---

## Final Resolved Code

```js
// change from CLONE 2
// change from clone 1

function add(a, b) {
  return Number(a) + Number(b);
}

console.log("Application started...");
