# Doctor Anywhere 🩺

**Doctor Anywhere** is a Flutter-based doctor appointment booking application. It helps patients find nearby clinics and doctors, view available appointment slots, and book appointments easily. The application also includes a front-office module where clinic staff can manage incoming appointment requests and confirm, reschedule, or cancel bookings.

## ✨ Features

### Patient App
- Patient registration and login
- Search for nearby clinics and doctors
- View doctor/clinic details
- Check available appointment time slots
- Book appointments
- View appointment history and booking status
- Receive booking confirmation status

### Front Office / Admin Panel
- View all incoming appointment requests
- Confirm, reschedule, or cancel appointments
- Manage daily patient appointment schedule
- View patient and doctor details
- Update appointment status

## 🛠️ Technology Stack

| Layer | Technology |
|---|---|
| Mobile Application | Flutter, Dart |
| State Management | Provider / Bloc / Riverpod *(update based on your project)* |
| Backend | PHP |
| API Communication | REST API, JSON |
| Database | MySQL *(update if different)* |
| Authentication | Token-based authentication / Firebase Authentication *(update based on your project)* |
| HTTP Requests | `http` package |

## 📱 Application Flow

1. The patient registers or logs in to the application.
2. The patient searches for a nearby clinic or doctor.
3. The patient selects a doctor and views available appointment slots.
4. The patient chooses a date and time slot and submits the appointment request.
5. The PHP backend validates the request and saves the appointment details.
6. The front-office staff views the new appointment request.
7. The front office confirms, reschedules, or cancels the appointment.
8. The patient can see the updated appointment status in the app.

## 🏗️ Project Architecture

The project follows a simple layered structure:

```text
lib/
├── main.dart
├── models/
│   ├── user_model.dart
│   ├── doctor_model.dart
│   ├── clinic_model.dart
│   └── appointment_model.dart
├── services/
│   ├── auth_service.dart
│   ├── doctor_service.dart
│   └── appointment_service.dart
├── providers/
│   ├── auth_provider.dart
│   └── appointment_provider.dart
├── screens/
│   ├── splash_screen.dart
│   ├── login_screen.dart
│   ├── register_screen.dart
│   ├── home_screen.dart
│   ├── doctor_list_screen.dart
│   ├── doctor_details_screen.dart
│   ├── booking_screen.dart
│   ├── appointment_history_screen.dart
│   └── front_office_dashboard.dart
└── widgets/
    ├── custom_button.dart
    ├── doctor_card.dart
    └── appointment_card.dart
```

## 🔌 API Endpoints

Example REST API endpoints used by the Flutter application:

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/register.php` | Register a new patient |
| `POST` | `/api/login.php` | Authenticate patient and return token |
| `GET` | `/api/doctors.php` | Get list of doctors/clinics |
| `GET` | `/api/available_slots.php` | Get available appointment slots |
| `POST` | `/api/book_appointment.php` | Create a new appointment booking |
| `GET` | `/api/appointments.php` | Get patient appointment history |
| `PUT` | `/api/update_appointment.php` | Confirm, reschedule, or cancel appointment |

### Example Booking Request

```json
{
  "doctor_id": 12,
  "patient_id": 35,
  "appointment_date": "2026-11-05",
  "appointment_time": "10:30 AM",
  "status": "pending"
}
```

### Example Booking Response

```json
{
  "success": true,
  "message": "Appointment booked successfully",
  "appointment_id": 108
}
```

## 🔐 Authentication

- Users log in using their email/phone number and password.
- After successful login, the backend returns an authentication token.
- The token is stored locally using **Flutter Secure Storage** or **SharedPreferences**.
- Authenticated API requests include the token in the request header.
- On logout, the token is removed and the user is redirected to the login screen.

Example header:

```http
Authorization: Bearer YOUR_AUTH_TOKEN
```

## ⚙️ Installation

### Prerequisites

Make sure you have the following installed:

- Flutter SDK
- Dart SDK
- Android Studio or VS Code
- Android Emulator or physical Android device
- PHP server such as XAMPP, WAMP, or Laravel Herd
- MySQL database

### Steps

1. Clone the repository:

```bash
git clone https://github.com/your-username/doctor-anywhere.git
cd doctor-anywhere
```

2. Install Flutter dependencies:

```bash
flutter pub get
```

3. Configure the backend URL.

Open the API service file and update the base URL:

```dart
const String baseUrl = "http://10.0.2.2/doctor_anywhere_api/api";
```

> Use `10.0.2.2` instead of `localhost` when testing from an Android emulator, because the emulator uses this address to access the local machine.

4. Import the database.

- Open phpMyAdmin.
- Create a database named `doctor_anywhere`.
- Import the provided SQL file:

```text
database/doctor_anywhere.sql
```

5. Run the Flutter app:

```bash
flutter run
```

## 📦 Dependencies

Add or update these packages in `pubspec.yaml`:

```yaml
dependencies:
  flutter:
    sdk: flutter
  http: ^1.2.0
  provider: ^6.1.2
  shared_preferences: ^2.2.3
  flutter_secure_storage: ^9.0.0
  intl: ^0.19.0
```

Run this after updating dependencies:

```bash
flutter pub get
```

## 🧪 Testing the Appointment Flow

1. Register a new patient account.
2. Log in using the registered credentials.
3. Search for a doctor or clinic.
4. Select an available date and time slot.
5. Book the appointment.
6. Log in to the front-office dashboard.
7. Confirm the appointment.
8. Check the patient appointment history to verify the updated status.

## 🚀 Future Improvements

- Google Maps integration for nearby clinic detection
- Push notifications for appointment confirmation and reminders
- Online payment integration
- Doctor availability management
- Patient medical records
- Rating and review system for doctors
- Admin analytics dashboard
- OTP-based login
- Multi-language support

## 📸 Screenshots

Add screenshots here after taking them from your app.

```text
screenshots/
├── login_screen.png
├── home_screen.png
├── doctor_list_screen.png
├── booking_screen.png
├── appointment_history_screen.png
└── front_office_dashboard.png
```

Example:

```markdown
![Login Screen](screenshots/login_screen.png)
![Doctor List](screenshots/doctor_list_screen.png)
```

## 🎥 Demo Video

Watch the complete application demo here:

[Add your YouTube/Google Drive demo video link here]

## 👨‍💻 Developer

**GURUPRASATH**  
Flutter Developer | PHP Backend Developer

- GitHub: https://github.com/GURUPRASATH02
- LinkedIn: https://www.linkedin.com/in/guruprasath02/
- Email: guruprasath2902@gmail.com

## 📄 License

This project was developed as an academy capstone project for learning and demonstration purposes.
