<!DOCTYPE html>
<html>
<head>
    <title>Test z Ochrany pred elektrickým prúdom</title>
    <script>
        function vyhodnotTest() {
            let spravne = 0;
            let celkovo = 100; // Počet otázok

            let odpovede = {};
            for (let i = 1; i <= 100; i++) {
                odpovede["q" + i] = "a"; // Predvolené správne odpovede
            }

            for (let key in odpovede) {
                let odpoved = document.querySelector('input[name="' + key + '"]:checked');
                if (odpoved && odpoved.value === odpovede[key]) {
                    spravne++;
                }
            }

            let percento = (spravne / celkovo) * 100;
            document.getElementById("vysledok").innerHTML = "Správne odpovede: " + spravne + "/" + celkovo + " (" + percento.toFixed(2) + "%)";
        }
    </script>
</head>
<body>
    <h2>Test z Ochrany pred elektrickým prúdom</h2>
    <form>
        <p>1. Aký je hlavný cieľ normy STN EN 61140?</p>
        <input type="radio" name="q1" value="a"> Zabezpečenie ochrany osôb pred zásahom elektrickým prúdom<br>
        <input type="radio" name="q1" value="b"> Definovanie typov elektrických ističov<br>
        <input type="radio" name="q1" value="c"> Určenie maximálneho prúdového zaťaženia vodičov<br>
        
        <p>2. Aký je rozdiel medzi SELV a PELV?</p>
        <input type="radio" name="q2" value="a"> SELV je bezpečné malé napätie bez uzemnenia, PELV môže mať uzemnený bod<br>
        <input type="radio" name="q2" value="b"> SELV je vyššie napätie ako PELV<br>
        <input type="radio" name="q2" value="c"> PELV nevyžaduje ochranné prvky<br>
        
        <p>3. Ktorá ochrana pred zásahom elektrickým prúdom využíva mechanické zábrany?</p>
        <input type="radio" name="q3" value="a"> Ochrana prekážkami<br>
        <input type="radio" name="q3" value="b"> Ochrana samočinným odpojením napájania<br>
        <input type="radio" name="q3" value="c"> Doplnková ochrana prúdovými chráničmi (RCD)<br>
        
        <p>4. Aká je bežná hodnota citlivosti prúdových chráničov (RCD) na ochranu osôb?</p>
        <input type="radio" name="q4" value="a"> 30 mA<br>
        <input type="radio" name="q4" value="b"> 100 mA<br>
        <input type="radio" name="q4" value="c"> 500 mA<br>
        
        <!-- Pridanie ďalších otázok až po 100 -->
        
        <br>
        <button type="button" onclick="vyhodnotTest()">Vyhodnotiť test</button>
    </form>
    <h3 id="vysledok"></h3>
</body>
</html>
