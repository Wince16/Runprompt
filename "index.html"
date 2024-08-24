// Fonctions pour générer les prompts
function generateManualPrompt() {
    const concept = document.getElementById('concept').value;
    const elements = document.getElementById('elements').value;
    const ambiance = document.getElementById('ambiance').value;
    const camera = document.getElementById('camera').value;
    const effets = document.getElementById('effets').value;

    const prompt = `A ${concept} featuring ${elements} with a ${ambiance} aesthetic. 
                    ${camera} captures the scene. The video incorporates ${effets} for visual impact.`;

    displayPrompt(prompt);
}

function generateRandomPrompt() {
    const concepts = ["futuristic cityscape", "underwater exploration", "magical forest"];
    const elements = ["flying cars", "bioluminescent creatures", "ancient trees"];
    const ambiances = ["cyberpunk", "mysterious", "whimsical"];
    const cameras = ["sweeping drone shots", "intimate handheld", "smooth tracking"];
    const effets = ["neon glows", "particle effects", "time distortions"];

    const prompt = `A ${randomChoice(concepts)} featuring ${randomChoice(elements)} with a ${randomChoice(ambiances)} aesthetic. 
                    ${randomChoice(cameras)} captures the scene. The video incorporates ${randomChoice(effets)} for visual impact.`;

    displayPrompt(prompt);
}

function randomChoice(array) {
    return array[Math.floor(Math.random() * array.length)];
}

function displayPrompt(prompt) {
    document.getElementById('prompt-output').innerHTML = `<strong>Prompt généré:</strong><br>${prompt}`;
}

function handleFileUpload() {
    const fileInput = document.getElementById('file-input');
    const fileType = document.getElementById('file-type').value;

    let prompt = "";
    if (fileType === "image") {
        prompt = `An image depicting [description of the image]. `;
        prompt += `Create a video that expands on the visual elements seen in the image. `;
        prompt += `Incorporate the color scheme, composition, and main subjects of the image into a dynamic video sequence. `;
        prompt += `The video should bring the static image to life, imagining movement and progression from the initial scene.`;
    } else if (fileType === "pdf") {
        prompt = `A document containing [description of the document's content]. `;
        prompt += `Create a video that visualizes the key concepts and information from the document. `;
        prompt += `Translate the main ideas into visual metaphors and scenes. `;
        prompt += `The video should capture the essence and mood of the document, using abstract or representative imagery to convey its message.`;
    }

    displayPrompt(prompt);
}

// Gestionnaires d'événements
document.getElementById('prompt-form').addEventListener('submit', function(e) {
    e.preventDefault();
    generateManualPrompt();
});

document.getElementById('random-button').addEventListener('click', generateRandomPrompt);

// Fonction pour gérer les onglets
function openTab(evt, tabName) {
    var i, tabcontent, tablinks;
    tabcontent = document.getElementsByClassName("tabcontent");
    for (i = 0; i < tabcontent.length; i++) {
        tabcontent[i].style.display = "none";
    }
    tablinks = document.getElementsByClassName("tablinks");
    for (i = 0; i < tablinks.length; i++) {
        tablinks[i].className = tablinks[i].className.replace(" active", "");
    }
    document.getElementById(tabName).style.display = "block";
    evt.currentTarget.className += " active";
}

// Ouvrir l'onglet "Manuel" par défaut
document.getElementsByClassName("tablinks")[0].click();

// Gestionnaire d'événement pour l'input de fichier
document.getElementById('file-input').addEventListener('change', function(e) {
    const fileName = e.target.files[0] ? e.target.files[0].name : "Aucun fichier sélectionné";
    console.log("Fichier sélectionné :", fileName);
});
