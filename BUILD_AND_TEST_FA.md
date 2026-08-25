# ساخت و آزمون

## پیش‌نیاز و caveat
Gradle برای اولین build باید dependency `org.vosk:vosk-android:0.3.47` و سایر dependencyها را یک‌بار از repository دریافت کند؛ این تنها caveat اینترنتی ساخت است. پس از cache شدن dependencyها و قرار دادن مدل روی دستگاه، runtime کاملاً آفلاین است. این پروژه targetSdk و minSdk سازگار با Android 8 / API 26 دارد و targetSdk آن 28 است.

## مدل و build
1. مدل کوچک فارسی را جداگانه download/extract کنید و در `app/src/main/assets/model-fa` قرار دهید.
2. در ریشه پروژه اجرا کنید: `./gradlew test`.
3. برای APK اجرا کنید: `./gradlew assembleDebug`.
4. نصب: `adb install -r app/build/outputs/apk/debug/app-debug.apk`.

بدون مدل، build ممکن است انجام شود ولی دکمه شنود عمداً خطای `مدل پیدا نشد: assets/model-fa` می‌دهد. مجوز RECORD_AUDIO باید در اولین اجرا پذیرفته شود. وجود و کیفیت افکت‌های نویز/اکو/AGC به سخت‌افزار و firmware دستگاه وابسته است؛ برنامه در نبود آنها crash نمی‌کند.

## عبارات آزمون
`پنتا طبقه ۱۰`، `پانتا منفی ۳`، `بنتا در را باز`، `چنتا فن روشن` و `چندتا چراغ خاموش`. تست parser بدون native Vosk در `VoiceParserTest.kt` انجام می‌شود.
