# معماری آفلاین

میکروفن با `AudioRecord` روی 16000Hz / mono / PCM16 خوانده می‌شود. هر قطعه به Recognizer Vosk داده می‌شود و JSON نتیجه در UI ثبت می‌گردد؛ متن `text` سپس به `VoiceParser` موجود داده می‌شود تا wake word و فرمان‌ها یک رفتار واحد داشته باشند. هیچ سرویس ابری یا Android SpeechRecognizer در مسیر runtime نیست.

مدل از `filesDir/model-fa` باز می‌شود و محل نصب توسعه آن `app/src/main/assets/model-fa` است. مدل در zip عمداً وجود ندارد.
