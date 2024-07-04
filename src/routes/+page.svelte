<script>
	import Steps from '../components/+steps.svelte';
	import Register from '../components/+register.svelte';
	import "../main.css";
</script>

    <div class="justify-center pt-20 pb-10">
      <div class="text-center">
        <span class="border border-dashed border-[#383838] bg-[#242424] text-md text-[#ccc] rounded-md px-4 py-2 font-regular">
          Developer-First Platform as a Service
        </span>
        <div>
          <div class="text-6xl font-bold space-y-3 mt-10 mb-4">
            <h1>Deploy your Svelte apps</h1>
            <h2 class="gradient-text">with <a class="zerops" target="_blank" href="https://zerops.io">Zerops</a></h2>
          </div>
          <p class="max-w-[800px] mx-auto text-2xl font-medium">
            Svelte example running on Zerops' Node.js service.<br/>
            Deploy and test yourself with a single click!
          </p>

          <div class="flex justify-center mt-12">
            <a
              href="https://app.zerops.io/recipe/svelte-nodejs"
              target="_blank"
              class="text-lg inline-block hover:no-underline text-white"
            >
              <span
                class="deploybutton rounded-full flex flex-row items-center justify-center space-x-4 hover:-translate-y-1 hover:duration-300 text-white"
              >
                <span>Deploy on Zerops</span>
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  enable-background="new 0 0 24 24"
                  height="22px"
                  viewBox="0 0 24 24"
                  width="24px"
                  fill="#fff"><g><rect fill="none" height="24" width="24"></rect></g><g><g><path d="M6,15c-0.83,0-1.58,0.34-2.12,0.88C2.7,17.06,2,22,2,22s4.94-0.7,6.12-1.88C8.66,19.58,9,18.83,9,18C9,16.34,7.66,15,6,15 z M6.71,18.71c-0.28,0.28-2.17,0.76-2.17,0.76s0.47-1.88,0.76-2.17C5.47,17.11,5.72,17,6,17c0.55,0,1,0.45,1,1 C7,18.28,6.89,18.53,6.71,18.71z M17.42,13.65L17.42,13.65c6.36-6.36,4.24-11.31,4.24-11.31s-4.95-2.12-11.31,4.24l-2.49-0.5 C7.21,5.95,6.53,6.16,6.05,6.63L2,10.69l5,2.14L11.17,17l2.14,5l4.05-4.05c0.47-0.47,0.68-1.15,0.55-1.81L17.42,13.65z M7.41,10.83L5.5,10.01l1.97-1.97l1.44,0.29C8.34,9.16,7.83,10.03,7.41,10.83z M13.99,18.5l-0.82-1.91 c0.8-0.42,1.67-0.93,2.49-1.5l0.29,1.44L13.99,18.5z M16,12.24c-1.32,1.32-3.38,2.4-4.04,2.73l-2.93-2.93 c0.32-0.65,1.4-2.71,2.73-4.04c4.68-4.68,8.23-3.99,8.23-3.99S20.68,7.56,16,12.24z M15,11c1.1,0,2-0.9,2-2s-0.9-2-2-2s-2,0.9-2,2 S13.9,11,15,11z"></path></g></g></svg>
              </span>
            </a>
          </div>
        </div>
      </div>
      <div class="flex justify-center pt-24">
        <Steps />
      </div>
      <p class="text-center mt-10 text-[#ccc]">
        Powered by{" "}
        <a class="link" href="https://zerops.io" target="_blank">
          Zerops
        </a>
      </p>
      <Register />
    </div>

<style>
	@import '../main.css';
</style>
