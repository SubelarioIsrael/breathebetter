# Breathe Better

Breathe Better is a Flutter-based mental health and wellness platform designed for students, guidance counselors, and administrators. The application provides mental health screening, mood tracking, sentiment analysis, guided breathing exercises, and counseling appointment scheduling with real-time chat and video calling.

---

## Key Features

### For Students
- **Clinical Screenings & Questionnaires**: Standardized mental health assessments based on GAD-7 (Generalized Anxiety Disorder) and PHQ-9 (Patient Health Questionnaire) metrics to monitor anxiety and depression trends over two-week windows.
- **Daily Mood Check-ins & Journaling**: Log emotions and thoughts daily. Entries can be analyzed via a backend sentiment analysis service to track emotional well-being over time.
- **Guided Breathing Exercises**: Interactive breathing sessions designed to help reduce acute stress and panic symptoms.
- **Counselor Directory & Appointment Booking**: Browse available counselors by department, book counseling sessions, and track upcoming appointments.
- **In-App Messaging & Video Consultations**: Direct chat and 1-on-1 video calling powered by ZEGOCLOUD UI Kit.
- **Support Contacts & Emergency Hotlines**: Immediate access to mental health hotlines and campus support resources.
- **Automated Wellness Chatbot**: Quick support and navigation assistance for common mental health inquiries.

### For Counselors
- **Student Case Management**: View assigned students, assessment histories, mood check-in trends, and journal progress.
- **Appointment Handling**: Accept, reschedule, complete, or cancel student counseling bookings.
- **Session Notes & Interventions**: Log clinical session notes, track interventions, and export reports to PDF.
- **Live Communication**: Real-time text messaging and video sessions with students.

### For Administrators
- **User & Account Management**: Manage student and counselor profiles, credentials, and department assignments.
- **Questionnaire & Content Management**: Update assessment questions, configure scoring scales, and publish wellness resources, daily uplifts, and hotline numbers.
- **System Monitoring**: Track platform activity and notifications across user roles.

---

## Tech Stack

- **Frontend**: Flutter (Dart 3+) for cross-platform Android & iOS support
- **Backend & Database**: Supabase (PostgreSQL, Auth, Realtime database, and Storage)
- **Video Calling**: ZEGOCLOUD Prebuilt Call SDK (`zego_uikit_prebuilt_call`)
- **Notifications**: OneSignal & Firebase Cloud Messaging (FCM)
- **Sentiment Analysis**: Microservice deployed on Render (analyzing journal sentiment)
- **Local Storage & State**: `shared_preferences`, standard Flutter controllers/services

---

## Project Structure

```
lib/
├── components/          # Reusable UI widgets and navigation drawers
├── constant/            # App constants and configuration
├── controllers/         # Business logic for admin, counselor, and student workflows
├── database/            # Supabase database clients and data mappers
├── models/              # Data models (Users, Appointments, Notes, Questionnaires, etc.)
├── pages/
│   ├── admin_new/       # Admin screens (User management, resource editing, content)
│   ├── counselor_new/   # Counselor screens (Overview, appointments, case notes)
│   ├── student_new/     # Student screens (Assessments, mood journal, booking, exercises)
│   └── chat/            # Real-time messaging and chat room views
├── services/            # Supabase API, sentiment analysis, notifications, video call services
├── utils/               # Responsive layouts, network connectivity, department helpers
└── widgets/             # Reusable UI elements, auth guards, avatars
```

---

## Getting Started

### Prerequisites
- [Flutter SDK](https://docs.flutter.dev/get-started/install) (version 3.2.3 or higher)
- [Android Studio](https://developer.android.com/studio) or VS Code with Flutter/Dart extensions
- Android device or Emulator (API level 21+) / iOS Simulator (macOS required)

### Configuration

Create or update `important_stuff.env` in the project root with the following keys:

```env
SUPABASE_URL=your_supabase_project_url
SUPABASE_ANON_KEY=your_supabase_anon_key
```

Ensure `important_stuff.env` is registered in `pubspec.yaml` under `assets:` (already configured by default).

### Installation & Run

1. **Clone the repository and navigate to the project root:**
   ```bash
   git clone <repo-url>
   cd breathe_better
   ```

2. **Install Flutter dependencies:**
   ```bash
   flutter pub get
   ```

3. **Start an emulator or connect a physical device:**
   ```bash
   flutter devices
   ```

4. **Run the application:**
   ```bash
   flutter run
   ```

---

## Assessment Scoring Guide

The student questionnaire uses a 5-point frequency scale reflecting symptoms experienced over the prior two weeks:

| Rating | Description |
| :---: | :--- |
| **1** | Not at all |
| **2** | Several days |
| **3** | More than half the days |
| **4** | Nearly every day |
| **5** | Every day |

Scores are combined to calculate standardized GAD-7 and PHQ-9 symptom severity indicators to assist counselors during evaluations.
