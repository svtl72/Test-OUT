<!DOCTYPE html>
<html lang="no">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>OUT Drammen</title>
    <style>
        :root { --primary: #2563eb; --success: #059669; --accent: #7c3aed; --bg: #f1f5f9; }
        body { font-family: -apple-system, system-ui, sans-serif; background: var(--bg); margin: 0; padding: 10px; }
        .kort { max-width: 450px; margin: 0 auto; background: white; padding: 20px; border-radius: 16px; box-shadow: 0 4px 12px rgba(0,0,0,0.1); }
        h1 { text-align: center; color: #1e3a8a; font-size: 20px; border-bottom: 2px solid var(--primary); padding-bottom: 10px; margin-top:0; }
        label { font-weight: bold; display: block; margin: 15px 0 5px; font-size: 12px; color: #4b5563; text-transform: uppercase; }
        select, input { width: 100%; padding: 14px; border: 2px solid #cbd5e1; border-radius: 10px; font-size: 16px; box-sizing: border-box; background: white; }
        .grid { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; }
        .grid-3 { grid-template-columns: 1fr 1fr 1fr; }
        .btn { background: #fff; border: 2px solid #cbd5e1; padding: 16px 5px; border-radius: 10px; font-weight: bold; cursor: pointer; color: #4b5563; font-size: 13px; -webkit-appearance: none; }
        .active { background-color: var(--primary) !important; color: white !important; border-color: #1e40af !important; }
        
        /* Ny knappestil for "Vært innom" */
        .quick-btn { background: var(--accent); color: white; border: none; width: 100%; padding: 15px; border-radius: 12px; font-size: 16px; font-weight: bold; margin-top: 10px; cursor: pointer; -webkit-appearance: none; display: flex; align-items: center; justify-content: center; gap: 8px; }
        .divider { margin: 25px 0; border-top: 2px dashed #cbd5e1; position: relative; }
        .divider span { position: absolute; top: -12px; left: 50%; transform: translateX(-50%); background: white; padding: 0 10px; color: #94a3b8; font-size: 12px; font-weight: bold; }

        #temaSection { display: none; background: #f8fafc; padding: 15px; border-radius: 10px; margin-top: 15px; border: 1px solid #cbd5e1; }
        .save-btn { background: var(--success); color: white; border: none; width: 100%; padding: 18px; border-radius: 12px; font-size: 18px; font-weight: bold; margin-top: 25px; cursor: pointer; -webkit-appearance: none; }
    </style>
</head>
<body>

<div class="kort">
    <h1>OUT Drammen 🚶‍♂️</h1>
    
    <label>1. Velg Sted</label>
    <select id="bydel">
        <option value="Bragernes">Bragernes</option>
        <option value="Gulskogen">Gulskogen</option>
        <option value="Konnerud">Konnerud</option>
        <option value="Krokstadelva">Krokstadelva</option>
        <option value="Mjøndalen">Mjøndalen</option>
        <option value="Solbergelva">Solbergelva</option>
        <option value="Strømsø">Strømsø</option>
        <option value="Åskollen">Åskollen</option>
        <option value="Åssiden">Åssiden</option>
        <option value="Fjell">Fjell</option>
        <option value="Svelvik">Svelvik</option>
    </select>

    <button type="button" class="quick-btn" id="btnQuick" onclick="lagre(true)">
        📍 VÆRT INNOM (Hurtig)
    </button>

    <div class="divider"><span>ELLER FULL REGISTRERING</span></div>

    <label>Ungdomsklubb</label>
    <select id="lokasjon">
        <option value="INGEN/GATA">INGEN (Ute i gata)</option>
        <option value="G60">G60</option>
        <option value="FELLESVERKET">FELLESVERKET</option>
        <option value="NEON">NEON</option>
        <option value="DOWN UNDER">DOWN UNDER</option>
        <option value="UNDERGRUNN">UNDERGRUNN</option>
        <option value="SKATTEKAMMERET">SKATTEKAMMERET</option>
        <option value="NØSTEDHALLEN">NØSTEDHALLEN</option>
    </select>

    <label>Type treff</label>
    <div class="grid">
        <button type="button" class="btn t-btn" onclick="velg('t', 'TREFF', this)">TREFF</button>
        <button type="button" class="btn t-btn" onclick="velg('t', 'SAMTALE', this)">SAMTALE</button>
    </div>

    <div id="temaSection">
        <label>Temaer</label>
        <select id="tema" style="height:150px" multiple>
            <option value="Alkohol">Alkohol</option>
            <option value="Bolig">Bolig</option>
            <option value="Cannabis">Cannabis</option>
            <option value="Familie">Familie</option>
            <option value="Forhold">Forhold</option>
            <option value="Fremtid">Fremtid</option>
            <option value="Fysisk helse">Fysisk helse</option>
            <option value="Kriminalitet">Kriminalitet</option>
            <option value="Psykisk helse">Psykisk helse</option>
            <option value="Rusmidler">Rusmidler</option>
            <option value="Vold">Vold</option>
            <option value="Økonomi">Økonomi</option>
            <option value="Skole">Skole</option>
            <option value="Informasjonsarbeid">Informasjonsarbeid</option>
        </select>
    </div>

    <label>Kjønn</label>
    <div class="grid grid-3">
        <button type="button" class="btn k-btn" onclick="velg('k', 'JENTE', this)">JENTE</button>
        <button type="button" class="btn k-btn" onclick="velg('k', 'GUTT', this)">GUTT</button>
        <button type="button" class="btn k-btn" onclick="velg('k', 'ANNET', this)">ANNET</button>
    </div>

    <label>Alder</label>
    <div class="grid grid-3">
        <button type="button" class="btn a-btn" onclick="velg('a', 'B-SKOLE', this)">B-SKOLE</button>
        <button type="button" class="btn a-btn" onclick="velg('a', 'U-SKOLE', this)">U-SKOLE</button>
        <button type="button" class="btn a-btn" onclick="velg('a', 'VGS', this)">VGS</button>
    </div>
    <div class="grid" style="margin-top:8px">
        <button type="button" class="btn a-btn" onclick="velg('a', '20-25 ÅR', this)">20-25 ÅR</button>
    </div>

    <label>Antall ungdommer</label>
    <input type="number" id="antall" placeholder="Eks: 5" inputmode="numeric">

    <button type="button" class="save-btn" id="btnLagre" onclick="lagre(false)">LAGRE FULL REGISTRERING</button>
</div>

<script>
    var valgt = { t: "", k: "", a: "" };

    function velg(kat, verdi, el) {
        document.querySelectorAll('.' + kat + '-btn').forEach(b => b.classList.remove('active'));
        el.classList.add('active');
        valgt[kat] = verdi;
        if(kat === 't') document.getElementById('temaSection').style.display = (verdi === 'SAMTALE' ? 'block' : 'none');
    }

    function lagre(isQuickVisit) {
        var btn = isQuickVisit ? document.getElementById('btnQuick') : document.getElementById('btnLagre');
        var sted = document.getElementById('bydel').value;

        // Validering basert på type lagring
        if(!isQuickVisit) {
            if(!valgt.t || !valgt.k || !valgt.a) {
                alert("Vennligst fyll ut alle felt for full registrering!");
                return;
            }
        }

        btn.disabled = true;
        btn.innerHTML = "Sender...";

        var formURL = "https://docs.google.com/forms/d/e/1FAIpQLScEs6BU3u2dsdpIkwnu6SwVhwKWfW-oH97LnYGUvZtHEb4y3Q/formResponse";
        var params = new URLSearchParams();
        
        // Felles felt
        params.append("entry.842257148", sted);

        if(isQuickVisit) {
            // Verdier for hurtigregistrering
            params.append("entry.214146964", "KUN INNOM"); // Lokasjon
            params.append("entry.1473666377", "VÆRT INNOM"); // Type treff
            params.append("entry.1346284831", "0"); // Antall
            params.append("entry.1163056236", "N/A"); // Alder
            params.append("entry.1511233883", "N/A"); // Kjønn
        } else {
            // Verdier for full registrering
            params.append("entry.214146964", document.getElementById('lokasjon').value);
            params.append("entry.1473666377", valgt.t);
            params.append("entry.1346284831", document.getElementById('antall').value);
            params.append("entry.1163056236", valgt.a);
            params.append("entry.1511233883", valgt.k);

            if(valgt.t === 'SAMTALE') {
                var temaer = Array.from(document.getElementById('tema').selectedOptions).map(o => o.value);
                temaer.forEach(t => params.append("entry.1946658553", t));
            }
        }

        fetch(formURL, {
            method: "POST",
            mode: "no-cors",
            headers: { "Content-Type": "application/x-www-form-urlencoded" },
            body: params.toString()
        }).then(() => {
            alert("Suksess! " + (isQuickVisit ? "Besøket" : "Registreringen") + " er lagret.");
            location.reload();
        }).catch(() => {
            alert("Noe gikk galt. Prøv igjen.");
            btn.disabled = false;
            btn.innerHTML = isQuickVisit ? "📍 VÆRT INNOM (Hurtig)" : "LAGRE REGISTRERING";
        });
    }
</script>
</body>
</html>
