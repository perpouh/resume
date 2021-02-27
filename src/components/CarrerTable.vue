<template>
  <table>
    <thead style="background-color: #ddd;">
      <tr>
        <th style="text-align: left">{{carrer.scale}}/{{carrer.role}}</th>
        <th style="text-align: left">{{carrer.start_ym}} 〜 {{carrer.end_ym}}</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td style="width:500px;">
          <h2>プロジェクト概要</h2>
          {{carrer.summary}}<br />
          <h2>担当フェーズ</h2>
          {{carrer.phase_in_charge || "-"}}
          <h2>業務内容</h2>
          <ul>
            <li v-for="content in carrer.business_content" :key="content">{{content}}</li>
          </ul>
          <h2>実績、取り組み</h2>
          {{carrer.achievement || "-"}}
        </td>
        <td>
          <ul>
            <li v-for="env in carrer.development_environment" :key="env">{{env}}</li>
          </ul>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default{
  props: ['carrer']
}
</script>

<style>
thead{
  background-color: #ddd;
}
th{
  text-align: left;
}
h2{
  font-size: 12pt;
}
</style>