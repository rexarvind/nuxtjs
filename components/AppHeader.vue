<template>
<header>
<nav v-bind="$attrs" :class="{ 'fixed-top' : fixed }" class="navbar navbar-expand-sm navbar-light bg-white border-bottom shadow py-1">
<div class="container">
<a class="navbar-brand fw-bold me-auto text-dark" href="#">
<img src="img/logo.webp" width="29" height="29" class="me-2 rounded" />Darpan Agarbatti</a>


<div class="dropdown d-sm-none">
<button class="btn btn-sm btn-primary " type="button" id="dropdownMenuButton1" data-bs-toggle="dropdown" aria-expanded="false">Menu</button>

<ul class="dropdown-menu dropdown-menu-end shadow" aria-labelledby="dropdownMenuButton1">

<li v-for="(navLink, index) in navLinks" :key="index">
<a class="dropdown-item" :href="navLink.url" target="_blank" rel="noopener noreferrer">
<img :src="'img/' + navLink.icon" height="27" class="me-2 bg-primary rounded p-1"/>

{{ navLink.title }}</a>
</li>

<li><hr class="dropdown-divider"></li>

<li><h6 class="dropdown-header">Find Us On Social Media & Amazon</h6></li>

<li><span class="dropdown-item-text">

<a v-for="(navSocialLink, index) in navSocialLinks" :key="index" :href="navSocialLink.url" :class="{'me-2' : index != navSocialLinks.length - 1}" class="btn btn-primary mb-2" target="_blank" rel="noopener noreferrer">
<img :src="'img/' + navSocialLink.icon" width="25" height="25" />
</a>



</span></li>

</ul>

</div>


<div class="collapse navbar-collapse fw-bold" id="navbarSupportedContent">
<ul class="navbar-nav ms-auto text-center">

<li class="nav-item">
<a class="nav-link" aria-current="page" href="#">Call Us</a>
</li>

<li class="nav-item">
<a class="nav-link" href="#">IndiaMart Store</a>
</li>

</ul>
</div>




</div>
</nav>
</header>
</template>

<script>
export default {

inheritAttrs: false,
props:{
  fixed:{type:Boolean,required:false,default:true}
},
data(){
  return{
    navLinks:[
    {title:'Call Us', icon:'call.png',
     url:'tel:+91-63781-60359'},
    {title:'IndiaMart Store', icon:'store.png',
     url:'https://m.indiamart.com/bh-entp-jodhpur/products-and-services.html'},
    ],
    navSocialLinks:[
    {title:'YouTube', icon:'youtube.png',
     url:'https://youtube.com/channel/UCca0B2fg6jscKp_Le4wH2_A'},
    {title:'Instagram', icon:'instagram.png',
     url:'https://www.instagram.com/darpanagarbatti/'},
    {title:'WhatsApp', icon:'whatsapp.png',
     url:'https://api.whatsapp.com/send?phone=916378160359'},
    {title:'Amazaon', icon:'amazon.png',
     url:'https://www.amazon.in/dp/B08NZSQVJ9/'},
    ],
  }
},
}
</script>