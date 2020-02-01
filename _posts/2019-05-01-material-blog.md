---
layout: post
title: Material Blog - stworzony przez programistę dla programistów
tags: [Blog, Open Source]
---

Prostota, szybkość, nowoczesność, modyfikowalny, konfiguracja w json, artykuły w html - w końcu programiści mają silnik pod bloga, który
spełnia ich potrzeby. Przyjrzyjmy się Material Blog - narzędzie dedykowane dla programistów.

Czym jest Material Blog? Prostymi słowy jest to nowoczesny szablon zaprojektowany dla programistów. Będąc np. frontend developerem chcielibyśmy mieć 
możliwość prostej i szybkiej modyfikacji wyglądu i działania naszego bloga. 
Dlatego podczas tworzenia Material Blog naszym założeniem było stworzenie bloga, który będzie:

* **Prosty w użyciu** - tak by nie poświęcać więcej niż 5 min na wdrożenie się w jego mechanizm
* **Łatwy do "customizacji"** - tylko podstawowe funckjonalności zostały zaimplementowany - reszta w rękach developerów
* **Prosty, przejrzysty, responsywny** - stawiamy na zawartość, a nie rzadko używane dodatkowe bajery
* **Darmowy, Open-Source** - siła w społeczeństwie!
* **Dedykowany dla IT** - dla swoich :)

Kliknij i zobacz [DEMO](http://materialblog.tech/)

## Jak zacząć go używać?

Przede wszystkim Blog został napisany w Angular, ale nie nie ma potrzeby znajomości tego frameworka do prowadzenia bloga. 
Zanim dodamy nasz pierwszy artykuł to musimy zainstalować silnik. W tym celu:

1. **Zacznijmy od instalacji Angular CLI on naszych maszynach.** 
Odpalamy tę komendę:
```
npm install -g @angular/cli
```
(Jeżeli nie mamy NodeJS to powinniśmy najpierw go zainstalować) 

2. **Klonujemy repo**
```
git clone https://github.com/delprzemo/angular-blog.git
```
3. **Instalujemy zależności** 
(w ścieżce, w której sklonowaliśmy repozytorium)
```
npm install
```
4. **Uruchamiamy aplikację.** 
W tym celu odpalamy ostatnią komendę:
```
ng serve
```

I to wszystko! Teraz możesz podejrzeć działający blog otwierając odpowiedni port localhost (domyślnie http://localhost:4200)

## Jak zacząć używać Material Blog?
Artkuły są trzymane w plikach HTML. Jeżeli nie czujesz się swobodnie używając HTML-a to są dostępne na sieci rózne edytory, które
tłumaczą zawartość na właśnie HTML. 
Aby dodać swój pierwszy artykuł:

1. Dodaj plik HTML w src/articles/html
2. Otwórz articles/article.service i dodaj metadane artykułu do zwracanego tam JSON-a. Tutaj przykładowy JSON:
```ts
return [
    {
        id: 1,
        title: 'Blog created by developer for developers',
        shortText: `Simple, customizable, fast, modern, configurable in json, articles in html -
        finally developers have blog template which is meeting their requirements.
        Time to look into Material Blog`,
        date: new Date(2019, 5, 1),
        html: "easy-blog.html",
        image: '/assets/blog-item.jpg',
        imageUrl: '',
        tags: ['Blog', 'Open source']
    },
```

I to wszystko - właśnie został stworzony pierwszy artykuł. Wystarczy dodać plik HTML i metadane w jsonie.
(W klonowanym repozytorium jest już kilka istniejących artykułów, na których można się wzorować)

### 1 Wskazówka
W celu dodania obrazka do artykułu użyj property 'image' po tym jak pobierzesz obrazek do folderu assets lub też
użyj property 'imageUrl' jeżeli chcesz się odwołać do zewnętrznej grafiki (posiadasz do niej link)

### 2 Wskazówka
Aby pokazać kod z tak zwaną "podświetloną składnią" to musimy użyć app-show-code component:

```html
‹app-show-code [lang]="'typescript'" style="color:white">
    class MyCode() {
        // example
    }
‹/app-show- code>
```

## Modyfikacja i dostosowanie do swoich potrzeb
Material Blog to prosty projekt zawierający jedynie podstawowe funkcjonalności, więc w szybki i wygodny sposób można dostosować go do swoich potrzeb,
dodawać nowe funckjonalności czy nawet zintegrować z innymi stronami. 

Można też zawsze użyć bazowej wersji, ale czy nie fajnie by było jakby nasz blog jednak trochę odróżniał się od innych? W tym celu prezentuję parę kroków,
po których troszkę odróżnimy nasz blog od innych:

1. Podmień **top-menu-img.jpg** w **src/assets** na swoje logo
2. Zmień tekst w górnym menu w **src/app/top-menu.component.html**
3. Poeksperymentuj w stylowanie top menu (**src/app/top-menu.component.less**)
Dla przykładu zmień kolor tła:
```css
.container-fluid {
    background-color: rgba(26, 119, 211, 1);
}
```
albo jego przeźroczystość:
```css
.top-img {
    opacity: 0.05;
}
```

Teraz, Twój blog będzie się trochę różnił od innych blogów :) 

## Opublikuj blog
To od Ciebie zależy gdzie opublikujesz swój blog. Ponieważ mechanizm Material Blog jest server-less więc wystarczy hosting jedynie dla statycznych stron.
Jest ich pełno. Ja osobiście polecam netlify.com gdzie wręcz absurdalnie łatwo jest skonfigurować CI/CD dla Twojego repozytorium, szczególnie jeżeli jest ono
na githubie. Po konfiguracji wystarczy wrzucić nowy artykuł do repozytorium by po chwili pojawił się opublikowany na internecie :)

### Naprawdę warto dzielić się wiedzą i doświadczeniem ze społecznością. Mam nadzieję, że ten blog sprawi, że będzie to łatwiejsze i ciekawsze! Udanej zabawy!