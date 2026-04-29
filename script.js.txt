const partidos = [
    {
        id: 1,
        local: "Barcelona",
        visitante: "Real Madrid",
        resultado: "2 - 1",
        stats: {
            posesion: "62%",
            tiros: 14,
            tirosPuerta: 6,
            faltas: 9
        }
    },
    {
        id: 2,
        local: "Manchester City",
        visitante: "Liverpool",
        resultado: "3 - 3",
        stats: {
            posesion: "55%",
            tiros: 18,
            tirosPuerta: 9,
            faltas: 11
        }
    }
];

const listaPartidos = document.getElementById("listaPartidos");
const statsContainer = document.getElementById("statsContainer");
const statsTitulo = document.getElementById("statsTitulo");
const statsLista = document.getElementById("statsLista");

partidos.forEach(p => {
    const card = document.createElement("div");
    card.className = "match-card";
    card.innerHTML = `
        <h3>${p.local} vs ${p.visitante}</h3>
        <p>Resultado: <strong>${p.resultado}</strong></p>
    `;
    card.onclick = () => mostrarStats(p);
    listaPartidos.appendChild(card);
});

function mostrarStats(partido) {
    statsTitulo.textContent = `${partido.local} vs ${partido.visitante}`;
    statsLista.innerHTML = `
        <li>Posesión: ${partido.stats.posesion}</li>
        <li>Tiros totales: ${partido.stats.tiros}</li>
        <li>Tiros a puerta: ${partido.stats.tirosPuerta}</li>
        <li>Faltas: ${partido.stats.faltas}</li>
    `;
    statsContainer.classList.remove("hidden");
}
