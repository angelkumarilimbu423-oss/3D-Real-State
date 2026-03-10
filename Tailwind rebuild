function rebuildBuilding() {
    // 1. Clear existing building
    while(buildingGroup.children.length > 0){ 
        buildingGroup.remove(buildingGroup.children[0]); 
    }

    const floors = parseInt(document.getElementById('floors').value);
    const size = parseInt(document.getElementById('size').value);
    const glassOpacity = parseInt(document.getElementById('glass').value) / 100;
    
    // UI Feedback
    document.getElementById('floor-val').innerText = floors;
    document.getElementById('size-val').innerText = size;
    document.getElementById('ai-status').innerText = `AI: Optimizing window-to-wall ratio for ${floors} floors. Simulating internal HVAC zones...`;

    const floorHeight = 3.5;
    
    for (let i = 0; i < floors; i++) {
        const yPos = (i * floorHeight) + (floorHeight / 2);

        // --- THE GLASS EXTERIOR ---
        const glassGeo = new THREE.BoxGeometry(size, floorHeight - 0.1, size);
        const glassMat = new THREE.MeshPhongMaterial({ 
            color: 0x88ccff, 
            transparent: true, 
            opacity: glassOpacity,
            shininess: 100,
            reflectivity: 1
        });
        const floorGlass = new THREE.Mesh(glassGeo, glassMat);
        floorGlass.position.y = yPos;
        buildingGroup.add(floorGlass);

        // --- THE CONCRETE CORE (INTERNAL) ---
        // This adds a solid center to the building
        const coreSize = size * 0.4;
        const coreGeo = new THREE.BoxGeometry(coreSize, floorHeight, coreSize);
        const coreMat = new THREE.MeshLambertMaterial({ color: 0x333333 });
        const core = new THREE.Mesh(coreGeo, coreMat);
        core.position.y = yPos;
        buildingGroup.add(core);

        // --- INTERNAL LIGHTS (The "AI" Glow) ---
        // Creates a glowing effect inside the glass
        const lightGeo = new THREE.BoxGeometry(size * 0.8, 0.1, size * 0.8);
        const lightMat = new THREE.MeshBasicMaterial({ 
            color: 0x60a5fa, 
            transparent: true, 
            opacity: 0.3 
        });
        const floorLight = new THREE.Mesh(lightGeo, lightMat);
        floorLight.position.y = yPos + (floorHeight / 2) - 0.2;
        buildingGroup.add(floorLight);

        // --- WINDOW FRAMES (Structural Edges) ---
        const edges = new THREE.EdgesGeometry(glassGeo);
        const frameLine = new THREE.LineSegments(
            edges, 
            new THREE.LineBasicMaterial({ color: 0xffffff, transparent: true, opacity: 0.5 })
        );
        frameLine.position.y = yPos;
        buildingGroup.add(frameLine);
    }
    
    // Update Stats
    document.getElementById('mesh-stats').innerText = `Elements: ${buildingGroup.children.length} | AI Rating: AAA`;
}
