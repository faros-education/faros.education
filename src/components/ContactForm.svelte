<script>

let badEmailFormat = false;

let email = "";
let message = ""


function validateEmail(){
    const expression = /(?!.*\.{2})^([a-z\d!#$%&'*+\-\/=?^_`{|}~\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF]+(\.[a-z\d!#$%&'*+\-\/=?^_`{|}~\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF]+)*|"((([ \t]*\r\n)?[ \t]+)?([\x01-\x08\x0b\x0c\x0e-\x1f\x7f\x21\x23-\x5b\x5d-\x7e\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF]|\\[\x01-\x09\x0b\x0c\x0d-\x7f\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF]))*(([ \t]*\r\n)?[ \t]+)?")@(([a-z\d\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF]|[a-z\d\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF][a-z\d\-._~\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF]*[a-z\d\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF])\.)+([a-z\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF]|[a-z\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF][a-z\d\-._~\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF]*[a-z\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF])\.?$/i;

    return expression.test(String(email).toLowerCase())
  }

function checkEmail(){
  let isNotValid = validateEmail();
  if (isNotValid){
    badEmailFormat = false;
  }
  else{
    badEmailFormat = true;
  }
}

function sendMessage(){
  // let date = new Date(Date.now()).toISOString();
  // try {
  //   debugger;
  //   await mutate(client, {
  //     mutation: ADD_TOOLREQUEST,
  //     variables: { email, message, date }
  //   });
  //   console.log("Document successfully written!");
  // } catch(error) {
  //   console.log("ERROR MUTATION");
  // }

  alert("This is where my graphql query would happen");
  alert("IF I HAD ONE");
}

</script>

<div class="box">

  <h3 class="title is-4">Contact Us</h3>
  <p class="subtitle" in:fly="{{ y: -50, duration: 1000 }}">
    Take advantage of our custom migration guides and transparent pricing
  </p>


  <label class="label is-pulled-left">Email</label>
  <div class="control has-icons-left has-icons-right">
    <input class="input" type="email" placeholder="Email" bind:value={email} class:is-danger="{badEmailFormat==true}" on:keyup={checkEmail}>
    <span class="icon is-small is-left">
      <i class="fas fa-envelope"></i>
    </span>
    <span class="icon is-small is-right" class:is-hidden="{badEmailFormat==false}">
      <i class="fas fa-exclamation-triangle"></i>
    </span>
  </div>
  <p class="help is-danger" class:is-hidden="{badEmailFormat==false}">This email is invalid</p>


  <label class="label is-pulled-left" style="margin-top: 10px;">Message</label>
  <div class="control">
    <textarea bind:value={message} class="textarea" placeholder="Tell us what you're looking for"></textarea>
  </div>

  <div class="columns" style="margin-top: 1rem;">
    <div class="column is-three-quarter"/>
    <div class="column is-one-quarter">
      <button class="button is-primary is-fullwidth" on:click={sendMessage}><strong>SUBMIT</strong></button>
    </div>
  </div>

</div>





<style>
textarea{
  margin-bottom: 100px;
  height:10px;
}

.box{
}
</style>
