## Prompt Structure and Experimental Details

Sections **A1** to **A7** contain the prompts for different question types, which are consistent across both surveys. Section **A8** provides the configuration details for *gemini-1.5-flash* and *gemini-pro*. Sections **A9** and **A10** cover experimental details and system requirements.

---

### A1. Radio Button Questions

#### Endpoint labeled

**Prompt by _Medium-II_ bot:**

Verhalte dich wie eine Person, die an einer Umfrage teilnimmt, und wähle eine passende Option basierend auf deren Denkweise/Eigenschaften für die folgende Frage:{question}

Dies ist eine Likert-Skala mit abgestuften Optionen, einschließlich leerer Optionen, die berücksichtigt werden sollten, um eine angemessene Abstufung zu wählen: {options}

Gib nur die Nummer der ausgewählten Option an, beginnend mit 1 für die erste Option.


**Prompt by _Advanced_ bot:**

Verhalte dich wie eine {age} Jahre alte {nature} deutschsprachige {gender} Person, die an einer Umfrage teilnimmt, und wähle eine passende Option basierend auf deren Denkweise/Eigenschaften für die folgende Frage: {question}

Dies ist eine Likert-Skala mit abgestuften Optionen, einschließlich leerer Optionen, die
berücksichtigt werden sollten, um eine angemessene Abstufung zu wählen: {options}

Gib nur die Nummer der ausgewählten Option an, beginnend mit 1 für die erste Option.

Berücksichtige dabei deine bisherigen Antworten: {history_part}



#### Fully labeled

**Prompt by _Medium-II_ bot:**

Verhalte dich wie eine Person, die an einer Umfrage teilnimmt, und wähle eine passende Option basierend auf deren Denkweise/Eigenschaften für die folgende Frage:{question}

Wähle eine der angegebenen Optionen: {options}


**Prompt by _Advanced_ bot:**

Verhalte dich wie eine {age} Jahre alte {nature} deutschsprachige {gender} Person, die an einer Umfrage teilnimmt, und wähle eine passende Option basierend auf deren Denkweise/Eigenschaften für die folgende Frage: {question}

Wähle eine der angegebenen Optionen: {options}

Berücksichtige dabei deine bisherigen Antworten: {history_part}


---

### A2. Checkbox Questions

**Prompt by _Medium-II_ bot:**

Verhalte dich wie eine Person, die an einer Umfrage teilnimmt, und wähle eine oder mehrere passende Option/en basierend auf deren Denkweise/Eigenschaften für die folgende Frage: {question}

Die folgenden Optionen stehen zur Auswahl: {options}

Gib eine oder mehrere ausgewählte Optionen als durch Kommas getrennte Liste zurück.


**Prompt by _Advanced_ bot:**

Verhalte dich wie eine {age} Jahre alte {nature} deutschsprachige {gender} Person, die an einer Umfrage teilnimmt, und wähle eine oder mehrere passende Option/en basierend auf deren Denkweise/Eigenschaften für die folgende Frage: {question}

Die folgenden Optionen stehen zur Auswahl: {options}

Gib eine oder mehrere ausgewählte Optionen als durch Kommas getrennte Liste zurück. 

Berücksichtige dabei deine bisherigen Antworten: {history_part}


---

### A3. Open Narrative Questions

**Prompt by _Medium-II_ bot:**
Verhalte dich wie eine Person, die an einer Umfrage teilnimmt, und schreibe eine Antwort auf Deutsch basierend auf deren
Denkweise/Eigenschaften für die folgende Frage: {question}

Gib eine kurze und prägnante Antwort.


**Prompt by _Advanced_ bot:**

Verhalte dich wie eine {age} Jahre alte {nature} deutschsprachige {gender} Person, die an einer Umfrage teilnimmt, und schreibe eine Antwort auf Deutsch basierend auf deren Denkweise/Eigenschaften für die folgende Frage: {question}

Gib eine kurze und prägnante Antwort.

Berücksichtige dabei deine bisherigen Antworten: {history_part}


---

### A4. Open Numeric Questions

**Prompt by _Medium-II_ bot:**

Verhalte dich wie eine Person, die an einer Umfrage teilnimmt, und gib eine präzise Antwort auf Deutsch basierend auf deren Denkweise/Eigenschaften für die folgende Frage: {question}

Gib die Antwort im genau geforderten Format, zum Beispiel nur Gewicht in kg, Jahr als Jahreszahl, usw


**Prompt by _Advanced_ bot:**

Verhalte dich wie eine {age} Jahre alte {nature} deutschsprachige {gender} Person, die an einer Umfrage teilnimmt, und gib eine präzise Antwort auf Deutsch basierend auf deren Denkweise/Eigenschaften für die folgende Frage: {question}

Gib die Antwort im genau geforderten Format, zum Beispiel nur Gewicht in kg, Jahr als Jahreszahl, usw.

Berücksichtige dabei deine bisherigen Antworten: {history_part}


---

### A5. Classification of Question

**Prompt by _Medium-II_ and _Advanced_ bot:**

Klassifiziere die folgende Frage in eine der folgenden Kategorien: ’attention check’, ’email’, ’opinion-based’. Verwende das genaue Format der angegebenen Kategorien.

1. attention check: Fragen, die explizite, spezifische Aktionen erfordern, um sicherzustellen, dass der Benutzer aufmerksam ist und den Instruktionen folgt. Diese Fragen enthalten klare Anweisungen, die ausgeführt werden müssen. Zum Beispiel: a. Klicke auf das Bild auf der Seite. b. Bitte gib das Wort ’Zustimmung’ im untenstehenden Textfeld ein. c. Bitte gib den Satz ’Ich weiß es nicht.’ im untenstehenden Textfeld ein. d. Wähle unabhängig vom Fragetext die zweite Option aus der Skala.
2. email: Fragen, die speziell nach der E-Mail-Adresse des Benutzers fragen. Zum Beispiel: a. Bitte gib eine E-Mail-Adresse an, um Updates zu erhalten. b.Wie lautet deine E-Mail-Adresse zur Kontoüberprüfung? c. Gib deine E-Mail-Adresse ein, um unseren Newsletter zu abonnieren.
3. Wenn die Frage keine spezifischen Aktionen oder Anweisungen enthält, wie in den Beispielen unter ’attention check’ beschrieben, und nicht nach einer E-Mail-Adresse fragt, wie in den Beispielen unter ’email’ beschrieben, klassifiziere sie als ’opinion-based’. Fragen, die allgemeine Informationen oder Meinungen erfragen und keine spezifischen Anweisungen beinhalten, fallen unter diese Kategorie.
   
Frage: {question}

Antworte im genauen Format der angegebenen Kategorien: ’attention check’, ’email’, ’opinion- based’.


---

### A6. Attention Checks as IMCs

**Prompt by _Medium-II_ and _Advanced_ bot:**
Attention checks erfordern explizite, spezifische Aktionen, um sicherzustellen, dass der Benutzer aufmerksam ist und den Instruktionen folgt. Klassifiziere den attention check in eine der folgenden Kategorien: ’image locator’, ’add keyword’, ’exact text’, ’radio button’. Verwende das genaue Format der angegebenen Kategorien.

1. Image locator: Fragen, bei denen der Benutzer auf ein Bild klicken muss. Zum Beispiel: a. Klicke auf das Bild auf der Seite. b. Klicke irgendwo auf das Umfragelogo.
2. Add keyword: Fragen, bei denen der Benutzer ein bestimmtes Schlüsselwort in ein Textfeld eingeben muss. Zum Beispiel: a. Bitte gib das Wort ’Zustimmung’ im untenstehenden Textfeld ein. b. Bitte gib die Zahlenkombination ’123456’ im untenstehenden Textfeld ein.
3. Exact text: Fragen, bei denen der Benutzer einen genauen Text in ein Textfeld eingeben muss. Zum Beispiel: a. Bitte gib den Satz ’Ich weiß es nicht.’ im untenstehenden Textfeld ein. b. Bitte gib den Satz ’Ich folge der Anweisung in der Frage.’ im untenstehenden Textfeld ein.
4. Radio button: Fragen, bei denen der Benutzer eine bestimmte Option klicken muss. Zum Beispiel: a. Wähle unabhängig vom Fragetext die zweite Option aus der Skala. b.Wähle unabhängig vom Fragetext die ’Weiß nicht’ Option.
Frage: {question}

Antworte im genauen Format der angegebenen Kategorien: ’image locator’, ’add keyword’, ’exact text’, ’radio button’.


---

### A7. CAPTCHA
Du bist ein Bildmodell. Bitte gib eine präzise Antwort auf die folgende Frage. Gib keine zusätzlichen Informationen oder Beschreibungen an, sondern beantworte genau das, was gefragt wird. Wenn du zum Beispiel gefragt wirst, wie viele Objekte im Bild
zu sehen sind, antworte mit einer Zahl, wie ’2’. Wenn du gefragt wirst, was du siehst, antworte mit dem genauen Namen der Objekte ohne zusätzliche Beschreibungen oder Kontext.

Frage: {question}


---

### A8. Gemini Parameters

```python
generation_config = {
    "temperature": 0.99,
    "top_p": 1,
    "top_k": 1,
    "max_output_tokens": 2048,
}
````
---
 ### A9. SurveyBot App Requirements

The app requires the **Google Chrome** browser and was compiled on a **Windows 10** system using an **Intel 10th Generation CPU**, making it usable on similar or newer systems.


---
### A10. Checkbox Results – LGBTQ Survey

**Combinations of Locations Selected by Medium-II and Advanced Bots (100 runs)**

| Selected Locations                                                          | Medium-II | Advanced |
|-----------------------------------------------------------------------------|-----------|----------|
| From house (including Home office)                                          | 96.0      | 96.0     |
| From house + At work (e.g., in the office)                                  | 2.0       | 1.0      |
| From house + In a public place (e.g., park or shopping center)              | 1.0       | 0.0      |
| From house + At a different place                                           | 1.0       | 3.0      |


