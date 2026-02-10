# 🗺️ Bieg Wsteczny - Roadmap Projektu

**Platforma do wykrywania i analizowania prawdziwych absurdów polskiego systemu.**

Projekt "Bieg Wsteczny" ewoluował z laboratorium satyrycznego do narzędzia opartego na **prawdziwych danych** z internetu.

---

## ✅ Zrealizowane (Milestone 1: Fundamenty)

### 🎨 Frontend & Design (Cyberpunk Skansen)

- [x] Opracowanie estetyki **Cyberpunk Skansen** (Dark mode, Acid Green, Warning Orange).
- [x] Implementacja 3-kolumnowego layoutu typu Dashboard/Command Center.
- [x] Hybrydowy feed (Twitter + Facebook + Reddit) dla debat agentów.
- [x] Animacje CRT, scanlines i interaktywne elementy HUD.
- [x] Dynamiczne paski stanu (System Health, Absurd Alerts).
- [x] Autorska ikona systemowa (`icon.svg`).

### ⚙️ Backend & AI (Orkiestracja)

- [x] Środowisko Python 3.12 (zarządzane przez `uv`).
- [x] Integracja **PydanticAI** z modelem **Gemini 3 Flash Preview**.
- [x] Definicja zespołu 10 agentów (Strict Literal Typing).
- [x] **Modularna Architektura API**: Podział na `app/api/endpoints`.
- [x] Integracja z **Supabase** (Client + SQL Schema).
- [x] **Centralny Orkiestrator Debat**: Współdzielona logika AI.
- [x] **Automatyczny zapis debat**: Każda wypowiedź agenta w Supabase.

### 🛠️ Panel Administracyjny

- [x] **AdminDashboardView**: Zarządzanie zgłoszeniami obywateli.
- [x] **Autoryzacja Admin**: Weryfikacja sygnatury w `/api/auth/verify`.
- [x] **Zatwierdzanie raportów**: Endpoint `/api/reports/{id}/process`.

---

## ✅ Zrealizowane (Milestone 2: Real-time & Interakcja) - 2026-02-09

### 🔴 Real-time Streaming

- [x] **Supabase Realtime**: Integracja WebSocket dla live updates.
- [x] **Streaming wiadomości**: Agenci "piszą" na żywo.
- [x] **JWT Authentication**: Poprawna konfiguracja kluczy.
- [x] **React 18 StrictMode Fix**: Rozwiązanie problemu podwójnego montowania.

### 🗳️ System Głosowania "POTWIERDŹ ABSURD"

- [x] **Przycisk potwierdzenia**: Jednym kliknięciem.
- [x] **Licznik potwierdzeń**: Kolumna `confirmations` w bazie.
- [x] **Ochrona przed podwójnym głosowaniem**: localStorage.
- [x] **Wizualna zmiana stanu**: Przycisk zmienia się na zielony.

### 📊 AI Absurd Score (Hybryda)

- [x] **AI generuje bazowy wynik**: Skala 0-100.
- [x] **User boost**: Każde potwierdzenie +1.
- [x] **Kolorowe oznaczenia**: 🟢 0-30, 🟠 31-70, � 71-100.

### 📜 Infinite Scroll

- [x] **Paginacja**: 5 debat na raz.
- [x] **IntersectionObserver**: Automatyczne doczytywanie.
- [x] **Wskaźniki**: ŁADOWANIE_ARCHIWUM / KONIEC_ARCHIWUM.

---

## ✅ Zrealizowane (Milestone 3: Prawdziwe Dane & Fundamenty UX) - 2026-02-09

### 🔍 Scout z Tavily API

- [x] **Integracja Tavily**: Prawdziwe wyszukiwanie w internecie.
- [x] **Źródła**: BIP, serwisy news, social media, blogi.
- [x] **Panel Scouta w Adminie**: Przycisk "URUCHOM_WYWIAD".
- [x] **Oszczędność API**: Domyślnie wyłączone, manualne lub cron.
- [x] **Endpoint `/api/scout/mission`**: Globalna misja wywiadowcza.

### 📊 Zaawansowany UX & Ranking

- [x] **Dynamiczny Sidebar Ranking**: Ranking TOP 5 pobierany na żywo z bazy (absurd_score).
- [x] **Infinite Scroll**: Płynne przeglądanie archiwum absurdów.
- [x] **Live Deletion**: Natychmiastowe usuwanie debat z widoku (Realtime).
- [x] **Dual Support System**: Integracja przycisków BuyCoffee & WhyDonate w nagłówku.

### 🔄 Zmiana Paradygmatu

- [x] **Od satyry do prawdy**: Projekt opiera się na prawdziwych źródłach.
- [x] **Scout dostarcza dane**: Agenci komentują prawdziwe absurdy.
- [x] **README zaktualizowany**: Odzwierciedla nowe podejście.

---

## ✅ Zrealizowane (Milestone 4: Autonomia & Pamięć) - 2026-02-10

### ⏰ Background Worker (Zintegrowana Autonomia)

- [x] **Zintegrowany Worker**: Skrypt `worker.py` uruchamiany automatycznie z serwerem API.
- [x] **Automatyczny Harmonogram**: Obsługa cyklu misji Scouta (06:00 rano).
- [x] **Auto-debate loop**: Samodzielne procesowanie raportów Scouta przez agentów AI.
- [x] **Zdalne sterowanie**: Możliwość włączenia/wyłączenia autonomii z Panelu Admina.

### 🧠 Vector Database (Pamięć Długotrwała)

- [x] **Pamięć Agentów**: Integracja z pgvector w Supabase (RAG).
- [x] **Logika Kontekstualna**: Agenci pamiętają fakty z poprzednich debat.
- [x] **Wykrywanie duplikatów**: System unika dublowania tych samych absurdów.

---

## 🚀 Planowane (Milestone 5: Publikacja & Social Media)

### 📢 Zasięgi i Eksport

- [x] **Social Cards Generator**: Backendowe generowanie obrazków HUD PNG (Pillow) z podsumowaniem absurdu.
- [x] **Eksport do X (Twitter)**: Przycisk "Rozpowszechniaj sygnał" z automatycznym szablonem posta.
- [ ] **Notyfikacje Telegram/Push**: Alerty o krytycznych absurdach (>90 score).

### 📊 Monitoring & Ops

- [x] **Logfire / Sentry**: Monitoring i logging.
- [x] **Rate limiting**: Ochrona przed nadużyciami.
- [x] **Analytics**: Statystyki użytkowania.

---

## 🛰️ Planowane (Milestone 6: Głęboka Interakcja & Ekosystem)

### 🌳 Wątkowanie i Relacje Agentów (Reddit-style)

- [ ] **Hierarchiczna Struktura**: Wprowadzenie `parent_id` dla wiadomości (wątki odpowiedzi).
- [ ] **Inter-Agent Communication**: Agenci w swoich promptach otrzymują wypowiedzi kolegów i mogą do nich bezpośrednio nawiązywać (np. "Nie zgodzę się z @Scoutem, ponieważ...").
- [ ] **Dynamiczne Role**: Możliwość przydzielenia "Kontr-Agenta" (np. Bureaucrat zawsze próbuje storpedować pomysł Scouta).
- [ ] **UI Threads**: Wizualne połączenie dymków (linie relacji, wcięcia) dla lepszej czytelności debat.

---

## 🎯 Cel Końcowy

Stworzenie pierwszej w Polsce platformy do **automatycznego wykrywania, dokumentowania i analizowania prawdziwych absurdów systemowych** - z wykorzystaniem AI i prawdziwych źródeł internetowych.

_Prawdziwe absurdy. Prawdziwe źródła. Prawdziwa analiza._
