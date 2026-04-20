<!DOCTYPE html>
<html lang="pt-PT">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Marcador de leitura para organizar livros lidos e nao lidos.">
  <title>Marcador de Leitura</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
      min-height: 100vh;
      color: #f6f0ff;
      background: linear-gradient(140deg, #3a0ca3 0%, #4361ee 45%, #4895ef 100%);
      padding: 24px;
    }

    .container {
      max-width: 920px;
      margin: 0 auto;
      background: rgba(13, 14, 36, 0.72);
      border: 1px solid rgba(255, 255, 255, 0.16);
      border-radius: 20px;
      box-shadow: 0 20px 60px rgba(11, 11, 31, 0.45);
      backdrop-filter: blur(6px);
      overflow: hidden;
    }

    header {
      padding: 34px 28px 22px;
      border-bottom: 1px solid rgba(255, 255, 255, 0.12);
    }

    header h1 {
      font-size: 2rem;
      margin-bottom: 8px;
    }

    header p {
      color: #d8d8ff;
      line-height: 1.6;
    }

    .deadline {
      margin-top: 12px;
      display: inline-block;
      background: rgba(114, 9, 183, 0.35);
      border: 1px solid rgba(255, 255, 255, 0.2);
      color: #f4e8ff;
      border-radius: 999px;
      padding: 8px 14px;
      font-size: 0.9rem;
      font-weight: 600;
    }

    main {
      padding: 26px 28px 30px;
    }

    .form-grid {
      display: grid;
      grid-template-columns: 1.2fr 1fr auto;
      gap: 12px;
      margin-bottom: 22px;
    }

    input[type="text"], select, button {
      border: 1px solid rgba(255, 255, 255, 0.16);
      border-radius: 12px;
      padding: 12px;
      font-size: 0.96rem;
      outline: none;
    }

    input[type="text"], select {
      background: rgba(255, 255, 255, 0.1);
      color: #ffffff;
    }

    input[type="text"]::placeholder {
      color: #d3d4ff;
    }

    select option {
      color: #111;
    }

    button {
      background: linear-gradient(120deg, #7209b7, #4361ee);
      color: #fff;
      font-weight: 700;
      cursor: pointer;
      transition: transform 0.2s ease, box-shadow 0.2s ease;
    }

    button:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 18px rgba(67, 97, 238, 0.45);
    }

    .toolbar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 16px;
      gap: 12px;
      flex-wrap: wrap;
    }

    .stats {
      color: #d8d8ff;
      font-size: 0.92rem;
    }

    .book-list, .search-list {
      list-style: none;
      display: grid;
      gap: 10px;
    }

    .book-item {
      background: rgba(255, 255, 255, 0.09);
      border: 1px solid rgba(255, 255, 255, 0.13);
      border-radius: 14px;
      padding: 14px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 10px;
    }

    .section-title {
      margin: 16px 0 10px;
      font-size: 1rem;
      color: #efe8ff;
      font-weight: 700;
    }

    .helper-text {
      font-size: 0.88rem;
      color: #c6c3ff;
      margin-bottom: 12px;
    }

    .search-meta {
      font-size: 0.86rem;
      color: #cbc9ff;
      margin: 6px 0 14px;
      min-height: 20px;
    }

    .book-title {
      font-size: 1rem;
      font-weight: 600;
    }

    .book-status {
      display: inline-block;
      margin-top: 6px;
      font-size: 0.82rem;
      padding: 3px 8px;
      border-radius: 999px;
      border: 1px solid rgba(255, 255, 255, 0.2);
    }

    .status-read {
      background: rgba(72, 149, 239, 0.3);
    }

    .status-unread {
      background: rgba(114, 9, 183, 0.3);
    }

    .book-actions {
      display: flex;
      gap: 8px;
      flex-wrap: wrap;
    }

    .small-btn {
      padding: 8px 10px;
      font-size: 0.83rem;
      border-radius: 10px;
    }

    .search-btn {
      background: linear-gradient(120deg, #4f46e5, #3b82f6);
    }

    .empty {
      text-align: center;
      color: #cbc9ff;
      padding: 28px 10px;
      border: 1px dashed rgba(255, 255, 255, 0.22);
      border-radius: 14px;
    }

    .hidden-signature {
      position: fixed;
      right: 14px;
      bottom: 10px;
      font-size: 0.75rem;
      letter-spacing: 0.4px;
      color: rgba(255, 255, 255, 0.16);
      user-select: none;
    }

    @media (max-width: 760px) {
      body {
        padding: 14px;
      }

      .form-grid {
        grid-template-columns: 1fr;
      }

      .book-item {
        flex-direction: column;
        align-items: flex-start;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <header>
      <h1>Marcador de Leitura</h1>
      <p>Site para escrever livros que queremos ler e marcar se ja foram lidos ou nao lidos.</p>
      <span class="deadline">Prazo do projeto: pronto ate quinta-feira</span>
    </header>

    <main>
      <form id="searchForm" class="form-grid">
        <input id="searchInput" type="text" placeholder="Pesquisar livro no catalogo mundial..." required>
        <select id="searchLimit" aria-label="Quantidade de resultados">
          <option value="10">10 resultados</option>
          <option value="20" selected>20 resultados</option>
          <option value="30">30 resultados</option>
        </select>
        <button type="submit" class="search-btn">Pesquisar</button>
      </form>

      <p class="helper-text">Pesquisa no acervo global da Open Library para marcar e desmarcar livros lidos e nao lidos.</p>
      <div class="search-meta" id="searchMeta">Sem pesquisa no momento.</div>
      <ul class="search-list" id="searchList"></ul>

      <h2 class="section-title">Os teus livros marcados</h2>
      <div class="toolbar">
        <div class="stats" id="statsText">0 livros | 0 lidos | 0 nao lidos</div>
        <select id="filterSelect" aria-label="Filtrar lista">
          <option value="todos">Mostrar todos</option>
          <option value="lido">Somente lidos</option>
          <option value="nao-lido">Somente nao lidos</option>
        </select>
      </div>

      <ul class="book-list" id="bookList"></ul>
      <div class="empty" id="emptyState">Ainda nao ha livros na lista.</div>
    </main>
  </div>

  <div class="hidden-signature">feito pela maria rocha do nono 7</div>

  <script>
    const searchForm = document.getElementById("searchForm");
    const searchInput = document.getElementById("searchInput");
    const searchLimit = document.getElementById("searchLimit");
    const searchList = document.getElementById("searchList");
    const searchMeta = document.getElementById("searchMeta");
    const filterSelect = document.getElementById("filterSelect");
    const bookList = document.getElementById("bookList");
    const statsText = document.getElementById("statsText");
    const emptyState = document.getElementById("emptyState");

    const STORAGE_KEY = "marcador-leitura-global";
    const idFactory = (window.crypto && typeof window.crypto.randomUUID === "function")
      ? () => window.crypto.randomUUID()
      : () => `${Date.now()}-${Math.random().toString(16).slice(2)}`;
    const markedBooks = loadMarkedBooks();
    let currentSearchResults = [];
    const fallbackBooks = [
      { key: "fallback-1", title: "Dom Quixote", author_name: ["Miguel de Cervantes"], first_publish_year: 1605 },
      { key: "fallback-2", title: "O Principe", author_name: ["Nicolau Maquiavel"], first_publish_year: 1532 },
      { key: "fallback-3", title: "Os Lusiadas", author_name: ["Luis de Camoes"], first_publish_year: 1572 },
      { key: "fallback-4", title: "Orgulho e Preconceito", author_name: ["Jane Austen"], first_publish_year: 1813 },
      { key: "fallback-5", title: "A Divina Comedia", author_name: ["Dante Alighieri"], first_publish_year: 1320 }
    ];

    function loadMarkedBooks() {
      try {
        const raw = localStorage.getItem(STORAGE_KEY);
        const parsed = raw ? JSON.parse(raw) : [];
        return Array.isArray(parsed) ? parsed : [];
      } catch (error) {
        return [];
      }
    }

    function saveMarkedBooks() {
      localStorage.setItem(STORAGE_KEY, JSON.stringify(markedBooks));
    }

    function buildBookLabel(book) {
      const author = book.author_name && book.author_name.length > 0
        ? book.author_name[0]
        : "Autor desconhecido";
      const year = book.first_publish_year || "Ano desconhecido";
      return `${book.title} - ${author} (${year})`;
    }

    function getMarkedByKey(key) {
      return markedBooks.find((item) => item.key === key);
    }

    function escapeHtml(text) {
      const div = document.createElement("div");
      div.textContent = text;
      return div.innerHTML;
    }

    function countStats() {
      const readCount = markedBooks.filter((book) => book.status === "lido").length;
      const unreadCount = markedBooks.length - readCount;
      statsText.textContent = `${markedBooks.length} livros | ${readCount} lidos | ${unreadCount} nao lidos`;
    }

    function renderMarkedBooks() {
      const activeFilter = filterSelect.value;

      const visibleBooks = markedBooks.filter((book) => {
        if (activeFilter === "todos") return true;
        return book.status === activeFilter;
      });

      bookList.innerHTML = "";

      if (visibleBooks.length === 0) {
        emptyState.style.display = "block";
      } else {
        emptyState.style.display = "none";
      }

      visibleBooks.forEach((book) => {
        const li = document.createElement("li");
        li.className = "book-item";

        const statusClass = book.status === "lido" ? "status-read" : "status-unread";
        const statusText = book.status === "lido" ? "Lido" : "Nao lido";

        li.innerHTML = `
          <div>
            <div class="book-title">${escapeHtml(book.title)}</div>
            <span class="book-status ${statusClass}">${statusText}</span>
          </div>
          <div class="book-actions">
            <button class="small-btn" data-action="toggle" data-id="${book.id}">Alternar estado</button>
            <button class="small-btn" data-action="remove" data-id="${book.id}">Remover</button>
          </div>
        `;

        bookList.appendChild(li);
      });

      countStats();
    }

    function renderSearchResults() {
      searchList.innerHTML = "";

      if (currentSearchResults.length === 0) return;

      currentSearchResults.forEach((book) => {
        const li = document.createElement("li");
        li.className = "book-item";
        const marked = getMarkedByKey(book.key);
        const statusText = marked ? (marked.status === "lido" ? "Lido" : "Nao lido") : "Nao marcado";
        const statusClass = marked
          ? (marked.status === "lido" ? "status-read" : "status-unread")
          : "status-unread";

        li.innerHTML = `
          <div>
            <div class="book-title">${escapeHtml(buildBookLabel(book))}</div>
            <span class="book-status ${statusClass}">${statusText}</span>
          </div>
          <div class="book-actions">
            <button class="small-btn" data-action="mark-read" data-key="${book.key}">Marcar lido</button>
            <button class="small-btn" data-action="mark-unread" data-key="${book.key}">Marcar nao lido</button>
            <button class="small-btn" data-action="unmark" data-key="${book.key}">Desmarcar</button>
          </div>
        `;

        searchList.appendChild(li);
      });
    }

    async function searchBooks(query, limit) {
      const encodedQuery = encodeURIComponent(query);
      const url = `https://openlibrary.org/search.json?q=${encodedQuery}&limit=${limit}`;

      const response = await fetch(url);
      if (!response.ok) throw new Error("Falha ao pesquisar livros.");

      const data = await response.json();
      return Array.isArray(data.docs) ? data.docs.filter((doc) => doc.key && doc.title) : [];
    }

    searchForm.addEventListener("submit", async (event) => {
      event.preventDefault();
      const query = searchInput.value.trim();
      if (!query) return;

      searchMeta.textContent = "A pesquisar no catalogo global...";
      searchList.innerHTML = "";

      try {
        const limit = Number(searchLimit.value);
        currentSearchResults = await searchBooks(query, limit);
        searchMeta.textContent = `${currentSearchResults.length} resultados encontrados para "${query}".`;
        renderSearchResults();
      } catch (error) {
        currentSearchResults = fallbackBooks.filter((book) => {
          const allText = `${book.title} ${(book.author_name || []).join(" ")}`.toLowerCase();
          return allText.includes(query.toLowerCase());
        });
        searchMeta.textContent = "Pesquisa online indisponivel. A mostrar resultados locais de emergencia.";
        renderSearchResults();
      }
    });

    filterSelect.addEventListener("change", renderMarkedBooks);

    bookList.addEventListener("click", (event) => {
      const target = event.target;
      if (!(target instanceof HTMLButtonElement)) return;

      const id = target.dataset.id;
      const action = target.dataset.action;
      if (!id || !action) return;

      if (action === "remove") {
        const index = markedBooks.findIndex((book) => book.id === id);
        if (index !== -1) markedBooks.splice(index, 1);
      }

      if (action === "toggle") {
        const selectedBook = markedBooks.find((book) => book.id === id);
        if (selectedBook) {
          selectedBook.status = selectedBook.status === "lido" ? "nao-lido" : "lido";
        }
      }

      saveMarkedBooks();
      renderMarkedBooks();
      renderSearchResults();
    });

    searchList.addEventListener("click", (event) => {
      const target = event.target;
      if (!(target instanceof HTMLButtonElement)) return;

      const key = target.dataset.key;
      const action = target.dataset.action;
      if (!key || !action) return;

      const sourceBook = currentSearchResults.find((book) => book.key === key);
      if (!sourceBook) return;

      const existing = getMarkedByKey(key);

      if (action === "unmark") {
        if (!existing) return;
        const index = markedBooks.findIndex((book) => book.key === key);
        if (index !== -1) markedBooks.splice(index, 1);
      } else {
        const nextStatus = action === "mark-read" ? "lido" : "nao-lido";
        if (existing) {
          existing.status = nextStatus;
          existing.title = buildBookLabel(sourceBook);
        } else {
          markedBooks.push({
            id: idFactory(),
            key,
            title: buildBookLabel(sourceBook),
            status: nextStatus
          });
        }
      }

      saveMarkedBooks();
      renderMarkedBooks();
      renderSearchResults();
    });

    renderMarkedBooks();
  </script>
</body>
</html>
