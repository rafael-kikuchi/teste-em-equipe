<template>
    <v-container>
        <div class="pesquisa">
            <v-text-field type="text" name="pais" id="pais" placeholder="Pesquise aqui o país"></v-text-field>
            <v-btn icon @click="pesquisarPais()" color="purple lighten-3">
                <v-icon>mdi-magnify</v-icon>
            </v-btn>
        </div>
        <v-simple-table v-if="pais">
            <template v-slot:default>
                <tbody>
                    <tr>
                        <th>País</th>
                        <td>{{pais.country}}</td>
                    </tr>
                    <tr>
                        <th>Casos</th>
                        <td>{{pais.cases}}</td>
                    </tr>
                    <tr>
                        <th>Casos de hoje</th>
                        <td>{{pais.todayCases}}</td>
                    </tr>
                    <tr>
                        <th>Óbitos</th>
                        <td>{{pais.deaths}}</td>
                    </tr>
                    <tr>
                        <th>Óbitos de hoje</th>
                        <td>{{pais.todayDeaths}}</td>
                    </tr>
                    <tr>
                        <th>Recuperados</th>
                        <td>{{pais.recovered}}</td>
                    </tr>
                    <tr>
                        <th>Ativos</th>
                        <td>{{pais.active}}</td>
                    </tr>
                    <tr>
                        <th>Críticos</th>
                        <td>{{pais.critical}}</td>
                    </tr>
                    <tr>
                        <th>Casos por milhão</th>
                        <td>{{pais.casesPerOneMillion}}</td>
                    </tr>
                    <tr>
                        <th>Óbitos por milhão</th>
                        <td>{{pais.deathsPerOneMillion}}</td>
                    </tr>
                    <tr>
                        <th>Testes totais</th>
                        <td>{{pais.totalTests}}</td>
                    </tr>
                    <tr>
                        <th>Testes por milhão</th>
                        <td>{{pais.testsPerOneMillion}}</td>
                    </tr>
                </tbody>
            </template>
            
        </v-simple-table>
        <p v-else class="my-3">País não selecionado!</p>
    </v-container>
</template>
<script>
export default {
    name: 'BuscarPais',
    data(){
        return{
            url: 'https://coronavirus-19-api.herokuapp.com/countries',
            pais: null
        }
    },
    methods: {
        pesquisarPais(){
            let nomePais = document.getElementById('pais').value;
            fetch(`${this.url}/${nomePais}`)
                .then(data => data.json())
                .then(json => this.pais = json)
                .catch(error => {
                    this.pais = null;
                    console.log(error);
                });
        }
    }
}
</script>
<style scoped>
    .pesquisa{
        display: flex;
        align-items: center;
    }
</style>