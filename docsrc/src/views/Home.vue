<template>
  <div class="page page--home">

    <section class="code">
      <h2>Install</h2>
      <div v-highlight><pre class="language-shell align-center"><code>npm i d3-vue-charts --save</code></pre></div>
    </section>

    <section class="chart">
      <D3BarChart :config="barconfig" :datum="bardata"></D3BarChart>
    </section>

    <section class="text">
      <h2>Introduction</h2>
      <p>vue-d3-charts is a charts module build with reusability in mind. It has evolved from a personal bl.ocks collection to a modular charts system, to allow quick implementations and high customatization charts.</p>
    </section>

    <section class="code">
      <h2>How to use</h2>
      <p>First import your desired charts:</p>
      <div v-highlight><pre class="language-javascript"><code>import {D3BarChart} from 'vue-d3-charts'</code></pre></div>
      <p>And then use it on your project, passing them a configuratioin object and a data array:</p>
      <div v-highlight><pre class="language-html"><code>{{bartext}}</code></pre></div>
      <p>Each chart has it's own configuration options. For example, the <strong>bar chart</strong> has these:</p>
      <div v-highlight>
        <pre class="language-javascript"><code>chart_config = {
  key: 'name',
  value: 'total',
  color: {current:'#41B882'},
  transition: {ease: 'easeBounceOut', duration: 1000}
}</code></pre>
      </div>
    </section>

    <ChartIndexComponent/>
    
    <section class="code">
      <h2>Common features</h2>
      <p>Each chart has its own features, but these are across all charts:</p>
      <SlopeChartExampleDataUpdate title="Data update" desc="Simply change your binding data as you want:"></SlopeChartExampleDataUpdate>
      <BarChartExampleBasic title="Reactive elements"></BarChartExampleBasic>
    </section>

  </div>
</template>

<script>
import {D3BarChart} from 'vue-d3-charts'

export default {
  name: 'HomeView',
  data(){
    return {
      bartext: '<D3BarChart :config="chart_config" :datum="chart_data"></D3BarChart>',
      titlechart: '<D3BarChart title="Your custom title"></D3BarChart>',
      sourcechart: '<D3BarChart source="Your custom source"></D3BarChart>',
      barconfig: {
        key: 'name',
        value: 'total',
        color: {current:'#41B882'},
        transition: {ease: 'easeBounceOut', duration: 1000}
      },
      bardata: [
        {name: '1992', total: 4748},
        {name: '1993', total: 5526},
        {name: '1994', total: 8574},
        {name: '1995', total: 15805},
        {name: '1996', total: 14582},
        {name: '1997', total: 26694},
        {name: '1998', total: 35205},
        {name: '1999', total: 45944},
        {name: '2000', total: 78595},
      ]
    }
  }
}
</script>
