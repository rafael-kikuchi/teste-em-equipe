<template>
    <div class="buscar-pais">
        <div class="pesquisa">
            <input type="text" name="pais" id="pais" placeholder="Pesquise aqui o país">
            <button @click="pesquisarPais()">Pesquisar</button>
        </div>
        
        <table v-if="pais">
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
        </table>
        <p v-else>País não selecionado!</p>
        <p v-if="pais">{{JSON.stringify(pais)}}</p>
    </div>
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

</style>