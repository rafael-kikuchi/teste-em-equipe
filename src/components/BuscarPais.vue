<template>
    <div class="buscar-pais">
        <div class="pesquisa">
            <input type="text" name="pais" id="pais" placeholder="Pesquise aqui o país">
            <button>Pesquisar</button>
        </div>
        
        <table>
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
    </div>
</template>
<script>
export default {
    name: 'BuscarPais',
    data(){
        return{
            pais: {
                country: "Brazil",
                cases: 21445651,
                todayCases: 18578,
                deaths: 597255, 
                todayDeaths: 455,
                recovered: 20425139,
                active: 423257,
                critical: 8318,
                casesPerOneMillion: 100007,
                deathsPerOneMillion: 2785,
                totalTests: 57282520,
                testsPerOneMillion: 267124
            }
        }
    }
}
</script>
<style scoped>

</style>