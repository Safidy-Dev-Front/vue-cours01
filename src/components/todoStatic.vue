 <template>
    <li>User {{userItem }}</li>
 </template>
 
 <script>
 export default{
     name: 'UserTodo',
    props: {
        userItem:Number
    }
 }
 </script>