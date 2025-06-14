# G11HUMSSSectionFinder
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Student Section Finder</title>
  <style>
    body { font-family: Arial, sans-serif; padding: 20px; background: #f2f2f2; }
    form { background: white; padding: 20px; max-width: 450px; margin: auto; border-radius: 8px; box-shadow: 0 0 10px rgba(0,0,0,0.1);}
    h2 { text-align: center; }
    label { display: block; margin-top: 10px; }
    input, select, button { width: 100%; padding: 10px; margin-top: 5px; }
    button { background: #007bff; color: white; border: none; border-radius: 4px; cursor: pointer; }
    #result { margin-top: 20px; text-align: center; font-size: 18px; }
  </style>
</head>
<body>
  <form id="studentForm">
    <h2>Find Your Section</h2>
    <label for="surname">Surname:</label>
    <input type="text" id="surname" required />
    
    <label for="givenName">Given Name:</label>
    <input type="text" id="givenName" required />
    
    <label for="gradeLevel">Grade Level:</label>
    <select id="gradeLevel" required>
      <option value="">Select Grade</option>
      <option value="11">Grade 11</option>
    </select>
    
    <button type="submit">Find Section</button>
    
    <div id="result"></div>
  </form>

  <script>
    const students = {
      "Grade 11": {
        "Aristotle": {
          adviser: "Mr. Phil Jay M. Duangon",
          names: [
            ["Agbay", "Fheb Vincent"],
            ["Almonte", "Kevin James"],
            ["Aparece", "Luiz Vergel"],
            ["Atillo", "Kurt"],
            ["Baang", "Kent Nathaniele"],
            ["Bacon", "Dennielle Jake"],
            ["Benarao", "Crismark"],
            ["Brizo", "Johnzyle"],
            ["Campugan", "Albert Jr."],
            ["Cuizon", "Ginoly"],
            ["Dayanan", "Cris Tof"],
            ["Fabe", "Rian"],
            ["Fernandez", "John Mark"],
            ["Gako", "Christian"],
            ["Irona", "Dave"],
            ["Lausa", "BB Jenboy"],
            ["Lauron", "Christian"],
            ["Lu- ang", "Richard Dems"],
            ["Nadela", "Jian James"],
            ["Pantilgan", "Jackris"],
            ["Racoma", "James Carl"],
            ["Remo", "Criss Michol"],
            ["Satinitigan", "June Vincent"],
            ["Satinitigan", "John Carlo"],
            ["Lauron", "Brian"],
            ["Tangaro", "Negro Patrick"],
            ["Traya", "James Rich"],
            ["Tumulak", "Kienneth"],
            ["Yurango", "Jushua Ray"],
            ["Amistad", "Mary Cris"],
            ["Cabungcal", "Krisha Marie"],
            ["Cabungcal", "Nechel Mae"],
            ["Dela Cerna", "Samantha"],
            ["Enad", "Sweet Kiel"],
            ["Erezo", "Kristel"],
            ["Espinosa", "Angelie"],
            ["Gabrillo", "Christ Jane"],
            ["Lapina", "Nikkie"],
            ["Lastima", "Merry Shane"],
            ["Lauron", "Shane"],
            ["Legarte", "Jhilia Mie"],
            ["Liniojan", "Beverly"],
            ["Lumogda", "Therese Vincene"],
            ["Mangubat", "Kimberly Jane"],
            ["Maputi", "Marie Cris"],
            ["Navacilla", "Nikha"],
            ["Navarro", "Chiecky Jayne"],
            ["Navarro", "Rona"],
            ["Naveo", "Maria Ivonne Regina"],
            ["Navoa", "Kisha Mae"],
            ["Pansan", "Fhebe Gail"],
            ["Parame", "Kylla"],
            ["Rafols", "Jermaine Denise"],
            ["Ricaplaza", "Chelsea"],
            ["Rudila", "Zairra"],
            ["Sabala", "Rhia Madjih"],
            ["Sasa", "Baby Jane"],
            ["Satinitigan", "Angie"],
            ["Tangaro", "Ella Mae"],
            ["Tanilon", "Princess Samantha"]
          ]
        },
        "Socrates": {
          adviser: "Mr. Clemente A. Villacastin, Jr.",
          names: [
            ["Aldaya", "Bhorly"],
            ["Babao", "Kim Lee Dave"],
            ["Babao", "John Emerson"],
            ["Bacalso", "Kyle Andrey"],
            ["Campugan", "Klent"],
            ["Camuro", "Renz"],
            ["Cuizon", "Louie Jay"],
            ["Escoto", "Nino Rey"],
            ["Fernandez", "John Lloyd"],
            ["Flores", "Dominic"],
            ["Lauron", "Ivan Roy"],
            ["Lauron", "Deejai Kyle"],
            ["Lauron", "Roien Vince"],
            ["Sipalay", "Daniel Cane"],
            ["Lausa", "John Khyl"],
            ["Manayaga", "Cyrus"],
            ["Maniego", "Mark Ethan"],
            ["Mortifero", "Shane"],
            ["Pantilgan", "Elijah Vincent"],
            ["Querubin", "Jahred"],
            ["Racoma", "Zeanne Carlo"],
            ["Rim", "Raven Zach"],
            ["Sabala", "Vincent"],
            ["Saraum", "June Jaren"],
            ["Satera", "Jemuel"],
            ["Satinitigan", "Rendy"],
            ["Siboco", "John Lenard"],
            ["Tangaro", "Jerald"],
            ["Villaren", "Jhun Vergel"],
            ["Ybanez", "Vaughn Uriel"],
            ["Aldaya", "Trisha Mae"],
            ["Blanco", "Cassie Zyrine"],
            ["Borja", "Rhosebhel Khay"],
            ["Cabungcal", "Jane Claire"],
            ["Campana", "Aira Mae"],
            ["Campugan", "Lady Jane"],
            ["Caparoso", "Princess Keziah"],
            ["Castanares", "Frencis Yancy"],
            ["Castanares", "Nichole Kerstine"],
            ["Conley", "Trisha Rose"],
            ["Dayondon", "Aveah"],
            ["Delgado", "Jade Althea"],
            ["Gabrillo", "Christ Joy"],
            ["Lagarnia", "Britney Blaze"],
            ["Larrobis", "Rachel"],
            ["Larrobis", "John Nes"],
            ["Larrobis", "Glyza Mae"],
            ["Lauron", "Alexa"],
            ["Lauron", "Hanna Jency"],
            ["Lausa", "Quency Bell"],
            ["Monacillo", "Chelsea"],
            ["Monopollo", "Michaela Mae"],
            ["Oaper", "Hannah Keziah"],
            ["Paldo", "Hannah Rucel"],
            ["Panugaling", "Gezel Myka"],
            ["Salcedo", "Kris Jean"],
            ["Santuyo", "Asia Gayle"],
            ["Satinitigan", "Glenndy Mae"],
            ["Tangkay", "Jennifer"],
            ["Tapic", "Mary Andrie"],
            ["Wamar", "Trisha Mae"]
          ]
        }
      }
    };

    document.getElementById("studentForm").addEventListener("submit", function (e) {
      e.preventDefault();
      
      const surname = document.getElementById("surname").value.trim().toLowerCase();
      const givenName = document.getElementById("givenName").value.trim().toLowerCase();
      const gradeLevel = document.getElementById("gradeLevel").value;

      const gradeKey = `Grade ${gradeLevel}`;
      const gradeData = students[gradeKey];
      let found = false;

      if (gradeData) {
        for (const [section, data] of Object.entries(gradeData)) {
          for (const [last, first] of data.names) {
            if (last.toLowerCase() === surname && first.toLowerCase() === givenName) {
              document.getElementById("result").innerHTML = 
                `<strong>Section:</strong> ${section}<br><strong>Adviser:</strong> ${data.adviser}`;
              found = true;
              break;
            }
          }
          if (found) break;
        }
      }

      if (!found) {
        document.getElementById("result").innerHTML = 
          `<span style="color:red;">Student not found. Please check the details.</span>`;
      }
    });
  </script>
</body>
</html>
