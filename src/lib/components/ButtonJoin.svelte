<script>
  let { buttonText, phoneNumber, defaultMessage } = $props();  
</script>

<div class="btn-box">
  <a href={`https://wa.me/${phoneNumber}?text=${defaultMessage}`} class="theme-btn btn-one">
    <span class="text">{buttonText}</span><i class="icon-3"></i>
    </a>
</div>
