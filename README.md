# Terese Wilhelmsen
!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Page Title</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Terese Wilhelmsen</h1>
    </header>
    <main>
        <p>Associate Professor
        </p>
        <p>Department of Educational Sciences
        </p>
        Faculty of Humanities, Sports and Educational Science,  
        </p> University of South-Eastern Norway.
    </main>
    <img src="C:\Users\tw\Pictures\TW bilde.png" alt="Picture" width="300" height="200">
</main>

    <nav>
        <ul>
            <li><a href="#about">About Me</a></li>
            <li><a href="#research">Research Interests</a></li>
            <li><a href="#publications">Publications</a></li>
            <li><a href="#cv">CV</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <!-- About Me Section -->
    <section id="about">
        <div class="container">
            <h2>About Me</h2>
            <p>I am a researcher specializing in educational sciences, motivational psychology, and sport and movement sciences. I currently work at the University of South-Eastern Norway, where I lead a research group focused on early childhood teacher education.</p>
            <p>Feel free to explore my research interests and publications below.</p>
        </div>
    </section>

    <!-- Research Interests Section -->
    <section id="research">
        <div class="container">
            <h2>Research Interests</h2>
            <ul>
                <li>Inclusive physical education</li>
                <li>Motivation in higher education</li>
                <li>Children's play and learning</li>
                <li>Sport for development and peace</li>
            </ul>
        </div>
    </section>

    <script src="https://d3js.org/d3.v6.min.js"></script>

    <section id="research-map">
        <div class="container">
            <h2>Interactive Research Map</h2>
            <svg id="research-map-svg" width="800" height="600"></svg>
        </div>
    </section>
    
    <script>
        const width = 800;
        const height = 600;

    
        const nodes = [
            { id: "Machine Learning" },
            { id: "Data Mining" },
            { id: "Computer Vision" },
            { id: "Natural Language Processing" },
            { id: "Reinforcement Learning" }
        ];
    
        const links = [
            { source: "Machine Learning", target: "Data Mining" },
            { source: "Machine Learning", target: "Reinforcement Learning" },
            { source: "Data Mining", target: "Computer Vision" },
            { source: "Computer Vision", target: "Natural Language Processing" }
        ];
    
        const svg = d3.select("#research-map-svg");
    
        const simulation = d3.forceSimulation(nodes)
            .force("link", d3.forceLink(links).id(d => d.id))
            .force("charge", d3.forceManyBody())
            .force("center", d3.forceCenter(width / 2, height / 2));
    
        const link = svg.selectAll(".link")
            .data(links)
            .enter().append("line")
            .attr("class", "link")
            .attr("stroke", "#ccc");
    
        const node = svg.selectAll(".node")
            .data(nodes)
            .enter().append("circle")
            .attr("class", "node")
            .attr("r", 10)
            .attr("fill", "#007bff")
            .call(d3.drag()
                .on("start", dragstarted)
                .on("drag", dragged)
                .on("end", dragended));
    
        node.append("title")
            .text(d => d.id);
    
        simulation
            .nodes(nodes)
            .on("tick", ticked);
    
        simulation.force("link")
            .links(links);
    
        function ticked() {
            link
                .attr("x1", d => d.source.x)
                .attr("y1", d => d.source.y)
                .attr("x2", d => d.target.x)
                .attr("y2", d => d.target.y);
    
            node
                .attr("cx", d => d.x)
                .attr("cy", d => d.y);
        }
    
        function dragstarted(event) {
            if (!event.active) simulation.alphaTarget(0.3).restart();
            event.subject.fx = event.subject.x;
            event.subject.fy = event.subject.y;
        }
    
        function dragged(event) {
            event.subject.fx = event.x;
            event.subject.fy = event.y;
        }
    
        function dragended(event) {
            if (!event.active) simulation.alphaTarget(0);
            event.subject.fx = null;
            event.subject.fy = null;
        }
    </script>

    <!-- Publications Section -->
    <section id="publications">
        <div class="container">
            <h2>Publications</h2>
            <p>Here are some of my most recent publications:</p>
            <ul>
                <li>Bjerknes, A. L., Wilhelmsen, T., & Foyn-Bruun, E. (2024). A Systematic Review of Curiosity and Wonder in Natural Science and Early Childhood Education Research. Journal of Research in Childhood Education, 38(1), 50-65. doi: https://doi.org/10.1080/02568543.2023.2192249.</li>
                <li>Thorjussen, I. M., & Wilhelmsen, T. (2024). Discourses of resistance: pre-service teachers’ reflections on the challenges of inclusion in physical education. Sport, Education and Society, 1-14. https://doi.org/10.1080/13573322.2024.2329570.</li>
                <li>Wilhelmsen, T., Bjerknes, A. L., & Moxnes, A. R. (2024). Pedagogical Impacts of Kindergartens’ Response to Covid-19. Nordic childhood educational research, 21(3), 360-380. https://doi.org/10.23865/nbf.v21.480.</li>
                <li>Wilhelmsen, T., Bjerknes, A. L., & Moxnes, A. R. (2024). Pedagogical Impacts of Kindergartens’ Response to Covid-19. Nordic childhood educational research, 21(3), 360-380. https://doi.org/10.23865/nbf.v21.480</li>
                <li>Wilhelmsen, T., Bjerknes, A. L. & Øvreås, S. (2024). Fra visjon til praksis: Å utøve nye struktur i barnehagelærerutdanning [From vision to practice: Implementing new structures in kindergarten teacher education]. I D. Husebø, L. Ferguson, O. R. Stalheim, I. C. Eriksen, K. R. Isaksen, A. Mavroudi & P.  Wallin (red.), Det universitets- og høgskolepedagogiske vitenskapsområdet i Norge – fremvekst, grunnlagstenkning og «state of the art» [The university and college pedagogical science area in Norway - emergence, basic thinking and "state of the art"]. Cappelen Damm Forskning (p. 337-360).  </li>  
                <li>Østmoen, J. P., & Wilhelmsen, T. (2024). Lekens lange linjer: En historisk analyse av lekbegrepet i læreplandokumenter for norske barnehager og skoler fra 1996 til 2020 [The long lines of play: A historical analysis of the concept of play in curriculum documents for Norwegian kindergartens and schools from 1996 to 2020]. Nordic Studies in Education, 44(2), 142-162. https://doi.org/10.23865/nse.v44.6248</li>   
            </ul>
        </div>
    </section>

    <!-- CV Section -->
    <section id="cv">
        <div class="container">
            <h2>Curriculum Vitae (CV)</h2>
            <p>Download my full CV here: <a href="cv.pdf" target="_blank">Download CV (PDF)</a></p>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <div class="container">
            <h2>Contact</h2>
            <p>If you'd like to get in touch, feel free to reach out via email:</p>
            <p><a href="mailto:terese.wilhelmsen@usn.no">terese.wilhelmsen@usn.no</a></p>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p>&copy; 2025 Terese Wilhelmsen. All rights reserved.</p>
            <div class="social-links">
                <a href="https://www.researchgate.net/profile/Terese-Wilhelmsen" target="_blank">ResearchGate</a>
                <a href="https://scholar.google.com/citations?hl=no&user=CXx2OtkAAAAJ" target="_blank">Google Scholar</a>
            </div>
        </div>
    </footer>

</body>

</html>
