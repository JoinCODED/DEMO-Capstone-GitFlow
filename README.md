# Technical Project Management

[slides](https://docs.google.com/presentation/d/1zop0bJo_8SeLXu_vPMBaSJz6AQHrBv0VoehdlPp6zKU)

## Git Flow Demo

#### Setup (before the demo)

- Create a team on joincoded's GitHub with all the students from the cohort ([here](https://github.com/orgs/JoinCODED/new-team))
- Give the team `write` permission for the [task repo](https://github.com/JoinCODED/Bootcamps/settings/collaboration)
- Create a new Trello board.
  - Sample board [Trello board](https://trello.com/b/dqOxvRMO/bootcamp-attendees)
- Give the students permission to access the board.
- Add the following trello cards to the backlog:
  - > `<Instructor>` will create a new cohort for `<Cohort>`
  - > `<Instructor>` will add lists for instructors and for students
  - > `<Instructor>` will add themselves to the instructors list
  - > `<Co-Instructor>` will add themselves to the instructors list
  - Per student:
    > `<Student>` will add themselves to the students list

#### The Feature Flow in Abstract

1. Show the current git flow  
   `clone(once) -> pull -> edit -> add -> commit -> push -> repeat...`  
   Show that there is a repo on github AND a repo on your local machine. `push` sends your _local_ changes to _Github_.  
   Explain why this is difficult to do with a team if everyone is going to be editing the same codebase at the same time.  
   It becomes hard to manage. Every time you want to commit or change anything you would need to pull and resolve conflicts first. Very time consuming.

2. Draw and explain the Feature Flow  
   `clone(once) -> pull -> branch -> edit -> add -> commit -> push -> merge`  
   This allows multiple people to work on multiple features, each in their own independent branch, avoiding conflicts until they're confident enough to merge.

#### Bootcamp Roster Demo

1. **The basic flow**

   Handle the card:

   > `<Instructor>` will create a new cohort for `<Cohort>`

   Use a proper git flow:

   - Move the card to doing
   - Create a branch `git checkout -b <feature-name>`
   - Try to do a push `git push` - it will fail because there's no remote branch specified
   - Do the initial push `git push -u origin <feature-name>` - explain that this creates the branch on Github and links this local branch to that remote one
   - Make the changes, add, commit
   - Push the changes `git push` - explain that you don't need to specify the branch any more because you already linked them using `-u`
   - Changes are on gitbub but still **not** on the master. Go to gihub and make a Pull Request
   - Show no conflicts, merge the code
   - Move the card to done

2. **The Reason Behind PRs**

   Hande the card:

   > `<Instructor>` will add lists for insturctors and for students

   Repeat the git flow, focusing on PRs:

   - Move the card to doing
   - Checkout + pull master - explain why you have to pull
   - Repeat the git flow but deliberately make sure you commit a typo
   - Show that the PR is an opportunity to reflect, review, discuss with the team before finalizing a commit:
     - Show the different tabs in the PR
     - Co-instructor catches the typo and leaves a message in the PR thread, tagging the instructor
     - Fix the typo, commit again, show that the _same_ open PR now has the new commit
   - Merge
   - Move the card to done

3. **Handling Conflict**

   Handle the cards:

   > `<Instructor>` will add themselves to the instructors list

   > `<Co-Instructor>` will add themselves to the instructors list

   - Both instructors move their cards
   - Both instructors checkout master, pull, make branches
   - Both instructors commit and make PRs
   - Show no conflict on **both** PRs
   - Merge the first PR
   - The second PR should now have a conflict
   - Show conflict resolution through GH
   - Merge the second PR

#### Bootcamp Roster Task

1. Ask students to go to the and clone the [repo](https://github.com/JoinCODED/Bootcamps).
2. Each student should handle their card from the trello board
