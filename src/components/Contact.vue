<template>
    <div>
      <h2>Contact Me</h2>
      <br/>
      <P>
        Name: Kaung Lynn Shann<br/><br/>
        Ph No: 09760789941<br/><br/>
        Email: kaungshann.forjob@gmail.com
      </P>
     <a :href="'mailto:' + emailAddress"><v-btn color="blue">Send Mail</v-btn></a>
    </div>
  </template>
  
  <script>
  export default {
  data() {
    return {
      emailAddress: 'kaungshann.forjob@gmail.com',
    };
  },
};
  </script>
  
