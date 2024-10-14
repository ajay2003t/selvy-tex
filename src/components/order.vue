<template>
  <div>
      <div class="contact-container">
        <!-- Left Side: Contact Information -->
        <div class="contact-info block-left">
          <h2 class="title">Contact US</h2>
          <div class="info">
            <div class="values">
              <h1 class="v-title"><img src="../assets/loca.png" class="img">Address</h1>
              <p class="v-desc">8/962, PN Rd, Karupparayan Nagar,<br>
                Tiruppur, India. 641603</p>
            </div>
            <div class="values">
              <h1 class="v-title"><img src="../assets/phone.png" class="img">Phone Number</h1>
              <p class="v-desc">+91 0000000000</p>
            </div>
            <div class="values">
              <h1 class="v-title"><img src="../assets/email.png" class="img">Email</h1>
              <p class="v-desc"><span style="color: black;font-weight: bold;">Email:</span>contact@selvytex.com</p>
            </div>
          </div>
          <div class="social-media">
            <h3 class="v-title">Follow us</h3>
            <div class="social-img">
              <a href=""><img src="../assets/instagram-brands-solid.svg" alt="Instagram" class="brands"></a>
              <a href=""><img src="../assets/youtube.svg" alt="YouTube" class="brands"></a>
              <a href=""><img src="../assets/twitter-brands-solid.svg" alt="Twitter" class="brands"></a>
            </div>
          </div>
        </div>
    
        <!-- Right Side: Contact Form -->
        <section class="contact-form">
          <div class="form-container">
            <h2 class="form-title">Send a Message</h2>
            <form @submit.prevent="submitForm">
              <div class="name-fields">
                <div class="input-group name-field">
                  <label for="firstName">First Name</label>
                  <input type="text" id="firstName" v-model="firstName" class="input-field-name"  required>
                </div>
                <div class="input-group name-field">
                  <label for="lastName">Last Name</label>
                  <input type="text" id="lastName" v-model="lastName" class="input-field-name"  required>
                </div>
              </div>
              <div class="input-group">
                <label for="email">Email</label>
                <input type="email" id="email" v-model="email" class="input-field" placeholder="Enter Your Email" required>
              </div>
              <div class="input-group">
                <label for="phone">Phone</label>
                <div class="phone-input">
                  <span class="country-code">+91</span>
                  <input type="tel" id="phone" v-model="phone" class="input-field" placeholder="Enter Phone Number" required>
                </div>
              </div>
              <div class="input-group">
                <label for="message">Message</label>
                <textarea id="message" v-model="message" class="input-field message-area" placeholder="Type Message..." required></textarea>
              </div>
              <button type="submit" class="submit-button">Submit <span class="arrow">➔</span></button>
            </form>
          </div>
        </section>
      </div>
    
    
  </div>
</template>

<script>
  export default {
    
  }
</script>

<style scoped>

@keyframes appear
{
    from
    {
        opacity: 0;
        scale: 0.1;
    }
    to
    {
        opacity: 1;
        scale: 1;
    }
}
.block
{
    animation :appear linear;
    animation-timeline: view();
    animation-range: entry 0;
}
@keyframes appearSideLeft
{
    from
    {
        opacity: 0;
        transform: translateX(-500px);
    }
    to
    {
        opacity: 1;
        transform: translateX(0px);
    }
}
.block-left
{
    animation :appearSideLeft linear;
    animation-timeline: view();
    animation-range: entry 0;
}
@keyframes appearSideRight
{
    from
    {
        opacity: 0;
        transform: translateX(500px);
    }
    to
    {
        opacity: 1;
        transform: translateX(0px);
    }
}
.block-right
{
    animation :appearSideRight linear;
    animation-timeline: view();
    animation-range: entry 0;
}
.brands
{
  width: 30px;
  height: 30px;
  margin-right: 10px;
  transition: transform 1s ease-in-out;
}
.brands:hover
{
  transform: translateY(-20px);
}
.img
{
  width: 40px;
  height: 40px;
  margin-right: 23px;
  transition: transform 1s ease-in-out;
}
.img:hover
{
  transform: translateY(-10px);
}
.v-title
{
  font-family: 'Outfit',sans-serif;
  font-size: 20px;
  font-weight: 400;
  color:#E07040;
}
.v-desc
{
  margin-bottom: 50px;
  font-family: 'Outfit',sans-serif;
  font-size: 16px;
  margin-left: 50px;
}

.contact-container {
  display: flex;
  padding-top: 50px;
  padding-bottom: 60px;
  /*justify-content: space-between;
  align-items: flex-start;
  padding: 40px;
  */
  flex-direction:row ;
  background-color: white;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  border-radius: 20px;
  width: 90%;
  /*max-width: 1200px;*/
  margin: 0 auto;
  margin-top: 2em;
  box-sizing: border-box;
  /*flex-wrap: wrap;*/
}

.contact-info {
  margin-left: 5%;
  margin-right: 40px;
  flex-basis: 35%;
  padding: 0em 3em;
  /*min-width: 250px;*/
  box-sizing: border-box;
}

.contact-info h2 {
  color: #e07040;
  margin-top: 60px;
  font-family: "Magra", sans-serif;
  font-size: 48px;
  font-weight: 700;
  text-align: center;
  margin-bottom: 20px;
}

.info {
  margin-top: 40%;
  font-size: 16px;
  line-height: 1.5;
}

.social-media {
  margin-top: 30px;
}

.social-img {
  display: flex;
  gap: 10px;
  margin-top: 10px;
}

.social-media h3 {
  color: #e07040;
  font-family: "Magra-Bold", Helvetica;
  font-size: 20px;
  font-weight: 700;
  margin-bottom: 10px;
}

.contact-form {
  width: 100%;
  flex-basis: 70%;
  /*max-width: 698px;*/
  margin: 0 auto;
  /*display: flex;
  justify-content: center;
  box-sizing: border-box;*/
  padding: 20px;
}

.form-container {
  background-color: #E07040;
  border-radius: 20px;
  padding-right: 20px;
  width: 92%;
  margin-right: 20px;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}

.form-title {
  color: #fff;
  font-family:'Magra', sans-serif;
  font-weight: bold;
  font-size: 48px;
  margin-top: 40px;
  margin-bottom: 40px;
  padding-top: none;
  margin-top: none;
  margin-left: 30%;
}

.name-fields {
  display: flex;
  margin-right: 1px;
  gap: 2px;
  width: 100%;
  border-collapse: separate;
  overflow: hidden;
  perspective: 1px;
  border-radius: 15px;
}

.name-field {
  flex: 1;
  border-collapse: separate;
  overflow: hidden;
  perspective: 1px;
  border-radius: 20px !important;
}


.input-group {
  display: flex;
  flex-direction: column;
  width: 90%;
  margin-bottom: 20px;
  margin-left: 2em;
  margin-right: 30px;
  padding-top: 10px;
  border-collapse: separate;
  overflow: hidden;
  perspective: 1px;
  margin-left: 40px;
  border-radius: 20px !important;
}

.input-group label {
  color: #fff;
  font-size: 15px;
  margin-bottom: 5px;
  padding-bottom: 5px;
  font-family: "Poppins", Helvetica;
}
.input-field-name::placeholder
{
  color: rgba(0, 0, 0, 0.5);
  font-family: "poppins",sans-serif;
  font-size: 14px;
}
.input-field::placeholder
{
  color: rgba(0, 0, 0, 0.5);
  font-family: 'poppins',sans-serif;
  font-size: 14px;
  letter-spacing: 2px;
  font-weight: lighter;
}
.input-field-name{
  width: 100%;
  padding: 15px;
  border: none;
  border-radius: 20px !important;
  background-color: #fff;
  font-size: 17px;
  border-collapse: separate;
  overflow: hidden;
  perspective: 1px;
  color: rgb(0, 0, 0);
  font-weight: 400;
}
.input-field {
  width: 90%;
  padding: 15px;
  border: none;
  border-radius: 20px !important;
  background-color: #fff;
  font-size: 17px;
  border-collapse: separate;
  overflow: hidden;
  perspective: 1px;
  color: rgb(0, 0, 0);
  font-weight: 400;
}

.phone-input {
  display: flex;
  align-items: center;
  background-color: #fff;
  border-radius: 20px !important;
  border-collapse: separate;
  overflow: hidden;
  perspective: 1px;
  padding: 0 25px;
  width: 90%;
}



.country-code {
  color: rgba(0, 0, 0, 0.8);
  font-size: 14px;
  margin-right: 5px;
}

.message-area {
  width: 90%;
  height: 107px;
  resize: vertical;
}

.submit-button {
  background-color: #fff;
  border: none;
  border-radius: 10px;
  color: rgba(0, 0, 0, 0.8);
  cursor: pointer;
  font-family: 'poppins',sans-serif;
  font-size: 16px;
  font-weight: 520;
  padding: 7px 30px;
  transition: background-color 0.3s ease;
  width: 36%;
  align-self: center;
  margin-top: 10px;
  margin-left: 35%;
  margin-bottom: 30px;
}

.submit-button:hover {
  background-color: #f0f0f0;
}

@media (max-width: 991px) {
  .contact-container {
    flex-direction: column;
    padding: 20px;
  }

  .contact-info, .contact-form {
    width: 100%;
    margin-bottom: 20px;
  }

  .form-container {
    padding: 20px;
  }

  .name-fields {
    flex-direction: column;
  }
}
input:focus {
    outline: none; /* Removes the default focus outline */
    box-shadow: none; /* Removes any custom focus shadow */
}
textarea:focus {
    outline: none; /* Removes the default focus outline */
    box-shadow: none; /* Removes any custom focus shadow */
}
.title
{
  position: relative;
  margin-bottom: 10%;
}

.title:hover::after
{
    width: 90%;
    cursor: pointer;
}
.submit-button
{
  transition: transform 0.3s ease;
}
.submit-button:hover
{
  transform: translateX(5px);
}


</style>