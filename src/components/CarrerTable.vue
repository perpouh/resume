<template>
  <table>
    <thead>
      <tr>
        <th>{{carrer.scale}}/{{carrer.role}}</th>
        <th>{{carrer.start_ym}} 〜 {{carrer.end_ym}}</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>{{carrer.summary}}</td>
        <td rowspan="4">
          <ul>
            <li v-for="env in carrer.development_environment" :key="env">{{env}}</li>
          </ul>
        </td>
      </tr>
      <tr><td>{{carrer.phase_in_charge}}</td></tr>
      <tr>
        <td>
          <ul>
            <li v-for="content in carrer.business_content" :key="content">{{content}}</li>
          </ul>
        </td>
      </tr>
      <tr><td>{{carrer.achievement}}</td></tr>
    </tbody>
  </table>
</template>

<script>
export default{
  props: ['carrer']
}
</script>