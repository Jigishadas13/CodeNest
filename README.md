# CodeNest- is your one-stop dashboard that aggregates competitive programming profiles from LeetCode, CodeChef, and CodeForces. Get a 360° view of your coding journey with unified statistics, combined heatmaps, and integrated contest calendars.

## ✨ Features

📊 Unified Analytics

Single-view dashboard for all platforms

Combined problem-solving statistics

Performance comparison across platforms

Rating progress visualization

## 🔥 Activity Heatmap

Unified coding activity visualization

Platform-specific activity breakdown

Custom date range selection

## 🗓 Contest Management

Aggregated contest calendar

Google Calendar integration

Contest reminders and notifications

Platform filter options

## ⚙️ User Experience

Customizable dashboard

Responsive design

Exportable statistics

## 📸 Screenshots
![image](https://github.com/user-attachments/assets/25641340-1089-4036-aa44-e6a7bd71ceed)

![image](https://github.com/user-attachments/assets/6e0616eb-f985-4e9f-bdda-d3d6c7449379)

![image](https://github.com/user-attachments/assets/30c8d252-e4d5-497e-b411-9f1836438825)

![image](https://github.com/user-attachments/assets/e0ce8a87-0a34-46c6-aa84-482bdb30a5b3)

![image](https://github.com/user-attachments/assets/db5b0352-0e30-4c35-a518-4a482214943b)

![image](https://github.com/user-attachments/assets/3b58c7e1-97f6-419e-a3d3-29c2305b8a0e)

![image](https://github.com/user-attachments/assets/7e96e208-b6ce-4ff0-8f5e-350086ce84c7)

![image](https://github.com/user-attachments/assets/a9efcd1f-e013-4c03-bc37-f6add3c3042e)

## 🛠 Tech Stack

### Frontend:

React.js

Tailwind CSS

### Backend:

Node.js

Express.js

Cheerio (Web scraping)

### Database:

Supabase (PostgreSQL)

## � Quick Start

Prerequisites

Node.js

npm

Supabase account

Supabase Database Setup

📊 Table Creation (SQL for Supabase Editor)

-- Profiles table

```
CREATE TABLE profiles (
    id UUID PRIMARY KEY REFERENCES auth.users(id),
    email TEXT,
    name TEXT,
    codeforces_username TEXT,
    codechef_username TEXT,
    leetcode_username TEXT,
    updated_at TIMESTAMPTZ,
    gender TEXT,
    location TEXT,
    education TEXT,
    github TEXT,
    linkedin TEXT
);
```

-- Total questions solved

```
CREATE TABLE total_questions (
    id UUID PRIMARY KEY REFERENCES profiles(id),
    leetcode_easy INT,
    leetcode_medium INT,
    leetcode_hard INT,
    leetcode_total INT,
    codechef_total INT,
    codeforces_total INT,
    created_at TIMESTAMPTZ DEFAULT now(),
    updated_at TIMESTAMPTZ DEFAULT now()
);
```

-- Contest ranking information

```
CREATE TABLE contest_ranking_info (
    id UUID PRIMARY KEY REFERENCES profiles(id),
    leetcode_recent_contest_rating NUMERIC,
    leetcode_max_contest_rating NUMERIC,
    codechef_stars NUMERIC,
    codechef_recent_contest_rating NUMERIC,
    codechef_max_contest_rating NUMERIC,
    codeforces_recent_contest_rating NUMERIC,
    codeforces_max_contest_rating NUMERIC,
    created_at TIMESTAMPTZ DEFAULT now(),
    updated_at TIMESTAMPTZ DEFAULT now()
);
```

🔐 Google Auth Setup for Supabase

☁️ Step 1: Configure Google Cloud Console

Visit Google Cloud Console.

Select or create a project.

Navigate to:

Click Create Credentials → OAuth 2.0 Client IDs.

Configure the consent screen:

User Type: External

Fill in necessary information (App name, support email, etc.)

Add your domain (if any) and developer contact info

Under Authorized redirect URIs, add :
    [https://<your-supabase-project-id>/auth/v1/callback.]
    
Replace <your-supabase-project-id> with your actual Supabase project ref.

Click Create, then copy:

Client ID

Client Secret

🔧 Step 2: Enable Google Auth in Supabase

Go to Supabase Dashboard.

Select your project.

Navigate to:

Paste the Client ID and Client Secret obtained from Google Cloud.

Toggle Google to Enable.

Click Save.

📌 Sample Redirect URI

https://abcd1234.supabase.co/auth/v1/callback

Installation

# Clone repository

git clone https://github.com/suveerprasad/cp-tracker.git

cd cp-tracker


# Install dependencies

cd frontend

npm install

cd backend

npm install

# Run the Project
cd frontend

npm run dev

cd backend

npm run dev







