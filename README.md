

# Props vs Data in Vue.js

In diesem Tutorial werden wir anhand von Beispielen den Unterschied zwischen Props und Daten kennen lernen.
## Props

Props werden verwendet, um die Daten von den übergeordneten Komponenten an die untergeordneten Komponenten zu übergeben.
Props sind schreibgeschützt, Wir können die Props nicht verändern.
Props werden innerhalb von Vue-Komponenten registriert, in dem die Props-Eigenschaft verwendet wird.

Beispiel:

    Welcome.vue

    <template>
        <h1>Welcome {{name}}</h1>
    </template>
    
    <script>
        export default{
            props:['name']    
            }
    </script>

In diesem Beispiel haben wir den Namen innerhalb der Willkommen Komponente registriert, registrierte Props können genau wie Dateneigenschaften innerhalb einer Vorlage verwendet werden.

Übergeben wir die Daten an die Willkommen Komponente.

    App.vue

    <template>
    <div id="app">
        <Welcome name="Gowtham"/>   </div>
    </tempalte>

Hier übergaben wir Daten an die Welcome Komponente unter Verwendung von name prop.
## Data

Die Daten, die wir innerhalb der Vue-Komponenten definiert haben, sind unabhängig von dieser Komponente, so dass wir nicht auf die Daten anderer Komponenten zugreifen oder sie verändern können.

Die einzige Möglichkeit, auf die Komponentendaten der anderen Komponenten zuzugreifen, ist die Verwendung von Props..

Daten sind in vue.js veränderbar, so dass vue, wenn wir die Dateneigenschaften aktualisieren, Ihre Komponente automatisch mit den aktualisierten Änderungen neu gerendert wird.

Beispiel:

Welcome.vue

    <template>
    <h1>Welcome {{name}}</h1>
    </template>
    
    <script>
    export default{
        props:['name']    
        }
    </script>

App.vue

    <template>
      <div>
        <Welcome :name="name" />    
        <button @click="changeName">Change name</button>
      </div>
    </template>
    
    <script>
    import Welcome from "./welcome.vue";
    export default {
      data: function() {
        return {
          name: "Gowtham"    
          };
      },
      methods: {
        changeName() {
          this.name = "Vue";
        }
      },
      components: { Welcome }
    };
    </script>

In der App-Komponente haben wir data property name mit name prop an die Welcome Komponente übergeben.

Wenn wir nun auf die Schaltfläche Name ändern klicken, wird die Eigenschaft name is property aktualisiert, so dass auch die Props der Willkommenskomponente mit dem neuen Wert aktualisiert werden.

Haben Sie bemerkt, dass die Dateneigenschaft einer App-Komponente die Stütze der Welcome Komponente sein wird?

Schlussfolgerung:

Die Daten sind für die Komponenten privat, und wir können mit Hilfe von Props auf diese Daten von anderen Komponenten zugreifen.
Die Daten sind veränderbar und die Props sind schreibgeschützt.

reactgo.com

