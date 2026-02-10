# 🏗️ Architektura Systemu Bieg Wsteczny

System został zaprojektowany w architekturze mikrousługowej, gdzie centralnym punktem jest moduł orkiestracji agentów.

## 1. Flow Zgłoszenia
1. **User/Scout Input**: Zgłoszenie trafia do bazy (Supabase).
2. **Orchestrator Service**: System buduje prompt wzbogacony o:
   - Wyniki wyszukiwania żywego internetu (Tavily).
   - Kontekst historyczny z bazy wektorowej (RAG).
3. **Agent Debate Cycle**:
   - Model Gemini generuje wielowątkową debatę między agentami.
   - Wynik jest strumieniowany do bazy wiadomości.
4. **Finalization**: System oblicza `absurd_score` i zapisuje embeddingi w pgvector.

## 2. Pamięć Wektorowa (RAG)
Używamy `pgvector` wewnątrz PostgreSQL do przechowywania embeddingów podsumowań debat. Dzięki temu agenci przy nowej analizie mogą otrzymać informację: *"Podobny przypadek analizowaliśmy 2 tygodnie temu w sprawie X"*.

## 3. Autonomiczny Worker
Niezależny proces (zintegrowany z FastAPI lifespan), który operuje na harmonogramie. Wykonuje on misje typu "Scout", które imitują zachowanie analityka przeglądającego codziennie serwisy informacyjne i portale legislacyjne.

## 4. Estetyka "Frontend First"
Główny interfejs opiera się na autorskim systemie CSS, który emuluje interfejsy CRT/HUD. Wszystkie komponenty Reactowe są zaprojektowane tak, aby sprawiać wrażenie pracy w terminalu wojskowym lub starej stacji badawczej.
