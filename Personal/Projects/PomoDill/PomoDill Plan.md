# 1. Product vision

**What Pomodill does**
- Helps users start focused study sessions quickly
- Encourages consistency with streaks, stats, and light gamification
- Makes studying feel less dull through pickle-themed visuals and rewards
- Works across phone, tablet, and browser so users can study anywhere

---

# 2. Platform plan

You want:
- **iPhone app**
- **iPad app**
- **web app**

Best product goal:
- same account across all platforms
- timer sessions sync to the cloud
- responsive layouts for phone, tablet, and desktop

A good approach would be:
- **Mobile + tablet:** iOS app
- **Web:** browser version with matching core features

---

# 3. Main feature set

## MVP features

These are the features you should launch with first.

### 1. Pomodoro timer

- Start focus session
- Short break
- Long break
- Customizable durations
- Pause, resume, skip
- Session complete animation

### 2. Task list

- Add study tasks
- Choose one task for current session
- Mark tasks complete
- Optional estimated pomodoros per task

### 3. Daily progress

- Number of sessions completed today
- Total focus time today
- Daily streak

### 4. Basic stats

- Focus time by day/week
- Number of completed sessions
- Most productive days

### 5. Themes / pickle branding

- Pickle jar progress visual
- Cute pickle mascot or icons
- Fun completion messages like:
    - “You’re kind of a big dill”
    - “Another crisp session complete”
    - “Stay cool as a cucumber”

### 6. Account + sync

- Sign in
- Save tasks, timer settings, and stats across devices

### 7. Notifications

- Session ended
- Break ended
- Reminder to come back and study

---

# 4. Post-launch feature ideas

These can come later.

### Gamification

- Earn pickles for finished sessions
- Unlock jars, backgrounds, mascot outfits
- Streak rewards
- Focus badges

### Study rooms / social

- Study with friends
- Shared timer room
	- See when friends are focusing q
- Leaderboards, maybe optional only
    

### Music / ambiance

- rain sounds
    
- café sounds
    
- lo-fi integration
    
- white noise
    

### Smart insights

- best study times
    
- weekly focus summaries
    
- suggestions based on habits
    

### Widgets / lock screen

- iPhone widget for quick start
    
- iPad home widget
    
- web dashboard widget panel
    

### Calendar integration

- plan focus blocks
    
- assign sessions to classes or subjects
    

---

# 5. App structure / pages

## A. Onboarding

Purpose: explain the app and get users into a session fast.

Sections:

- Welcome to Pomodill
    
- Choose your goal:
    
    - studying
        
    - homework
        
    - reading
        
    - work
        
- Set default timer lengths
    
- Create account or continue as guest
    

## B. Home / Timer page

This is the main page.

Should include:

- large timer
    
- current mode: focus / short break / long break
    
- start / pause / reset
    
- selected task
    
- session progress
    
- quick stats for the day
    
- pickle-themed visual element
    

This is the most important screen.

## C. Tasks page

- Add tasks
    
- Organize by subject or category
    
- Select task for next session
    
- Completed tasks section
    

Optional:

- drag reorder
    
- assign due dates
    
- estimate number of pomodoros
    

## D. Stats page

- daily focus time
    
- weekly chart
    
- streak count
    
- completed sessions
    
- subject breakdown
    

Could also include:

- “Your best dill of the week”
    
- “Most focused day”
    

## E. Rewards / Collection page

- unlocked pickle jars
    
- badges
    
- streak rewards
    
- character customization
    

Not needed for MVP, but great for personality.

## F. Settings page

- focus length
    
- short break length
    
- long break length
    
- sessions before long break
    
- sounds
    
- notifications
    
- theme
    
- account sync
    

## G. Profile page

- username
    
- streak
    
- total study time
    
- favorite subject
    
- achievements
    

## H. Web dashboard

For web, this can mirror the mobile experience but take advantage of larger screen space:

- timer in center
    
- task list on left
    
- stats on right
    
- session history below
    

---

# 6. Suggested navigation

## iPhone

Use a **bottom tab bar**.

Tabs:

- Timer
    
- Tasks
    
- Stats
    
- Rewards
    
- Settings
    

## iPad

Use a **sidebar layout** for better use of space.

Sidebar:

- Timer
    
- Tasks
    
- Stats
    
- Rewards
    
- Settings
    

Main content:

- selected page content
    
- timer can remain pinned in some sections
    

## Web

Use a left sidebar + main dashboard layout.

This is probably the best structure for desktop.

---

# 7. Timer experience design

The timer flow should feel satisfying.

## Focus session flow

1. User opens app
    
2. Selects or creates a task
    
3. Presses start
    
4. Timer runs with subtle animation
    
5. Session ends
    
6. Celebration screen appears
    
7. App moves to break mode
    
8. After break, user starts next session
    

## Small delight ideas

- pickle filling up a jar as time passes
    
- pickle mascot gets “more focused”
    
- subtle crunch/pop animation on completion
    
- funny productivity messages
    

Keep these optional so serious users are not annoyed.

---

# 8. Pickle theme ideas

You need a strong brand without hurting usability.

## Visual language

- greens, cream, light yellow
    
- jar glass effect
    
- rounded UI
    
- simple cartoon iconography
    
- clean typography
    

## Possible UI metaphors

- **Jar = daily progress**
    
- **Pickles earned = completed sessions**
    
- **Brine level = current focus streak**
    
- **Pickle badges = achievements**
    

## Copy ideas

- “Let’s get in a pickle”
    
- “Time to focus, big dill”
    
- “Stay crisp”
    
- “Brine and grind”
    
- “You crushed that session”
    

Use lightly, not everywhere.

---

# 9. Key user flows

## Flow 1: quick study start

- open app
    
- tap start
    
- focus session begins immediately
    

This should be frictionless.

## Flow 2: study with task

- open app
    
- select task
    
- start timer
    
- task gets linked to session
    
- progress saved
    

## Flow 3: review progress

- open stats
    
- see focus time, streaks, and completed sessions
    
- feel motivated to continue
    

## Flow 4: return user reminder

- user gets reminder notification
    
- taps notification
    
- app opens directly to timer
    

---

# 10. MVP page breakdown

If you want to keep the first version lean, build only these:

### Must-have

- Onboarding
    
- Login / guest
    
- Home / Timer
    
- Tasks
    
- Stats
    
- Settings
    

### Nice but later

- Rewards
    
- Friends/social
    
- advanced analytics
    
- deep customization
    
- study groups
    

---

# 11. Recommended data model

At a high level, your app will likely need:

## User

- id
    
- name
    
- email
    
- avatar
    
- created_at
    

## TimerSettings

- focus_duration
    
- short_break_duration
    
- long_break_duration
    
- sessions_until_long_break
    
- auto_start_breaks
    
- auto_start_sessions
    

## Task

- id
    
- user_id
    
- title
    
- subject
    
- estimated_sessions
    
- completed
    
- due_date
    

## Session

- id
    
- user_id
    
- task_id
    
- type (focus, short_break, long_break)
    
- duration
    
- completed
    
- started_at
    
- ended_at
    

## Achievement

- id
    
- user_id
    
- badge_type
    
- unlocked_at
    

---

# 12. Feature prioritization

## Phase 1: MVP

- timer
    
- tasks
    
- stats
    
- login
    
- sync
    
- notifications
    
- basic pickle theme
    

## Phase 2

- achievements
    
- streak rewards
    
- iPad optimized layouts
    
- improved charts
    
- widgets
    

## Phase 3

- study rooms
    
- friends
    
- shared sessions
    
- calendar integrations
    
- premium features
    

---

# 13. Monetization ideas

Only if you want it.

## Free

- timer
    
- tasks
    
- basic stats
    
- 1 or 2 themes
    

## Premium

- advanced analytics
    
- more themes
    
- more sounds
    
- custom mascot items
    
- deeper history
    
- cross-device productivity reports
    

Keep free version genuinely useful.

---

# 14. Tech planning direction

Since you want **iPhone + iPad + web**, your options are basically:

## Option A: one shared codebase approach

Good if you want faster development and shared logic.

## Option B: separate native iOS + separate web

Good if you want stronger platform-specific polish, but more work.

For a project like this, a shared approach is usually very practical, especially early on.

---

# 15. Design priorities

The app should be:

- fast to start
    
- visually calming
    
- playful but not distracting
    
- very easy to understand in under 10 seconds
    

That means:

- large timer
    
- clear buttons
    
- minimal clutter
    
- strong contrast
    
- theme accents, not theme overload
    

---

# 16. Example information architecture

Here’s a clean sitemap:

**Pomodill**

- Onboarding
    
- Auth
    
- Timer
    
- Tasks
    
    - Active tasks
        
    - Completed tasks
        
- Stats
    
    - Daily
        
    - Weekly
        
    - Monthly
        
- Rewards
    
    - Badges
        
    - Themes
        
- Settings
    
    - Timer settings
        
    - Notifications
        
    - Account
        
    - Appearance
        

---

# 17. Best first version

If I were planning the first version, I’d make it this:

## Pomodill v1

- cute onboarding
    
- one polished timer screen
    
- simple task management
    
- daily and weekly stats
    
- login + sync
    
- push notifications
    
- pickle jar progress illustration
    
- streak tracking
    

That is enough to feel like a real product.

---

# 18. Brand direction summary

**Pomodill** should feel like:

- Duolingo’s charm
    
- a study app’s simplicity
    
- a habit app’s motivation
    
- a cozy playful green aesthetic
    

---

# 19. Next step I recommend

The best next move is to define:

1. exact MVP features
    
2. page-by-page wireframes
    
3. user flow
    
4. tech stack
    

I can map out **the full MVP wireframe and screen-by-screen layout for Pomodill** next.