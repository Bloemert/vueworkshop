<template>
  <div class="wrapper">
    <center>
      <div class="header">
        <div class="inner">
          <div class="StepSelector">
            <label for="step">Choose a step:</label>
            <select id="step" v-model="currentStep" @change="stepChange">
              <option value="Step-0_Welcome_Goal.md">
                Step 0 - Welcome & Goals
              </option>
              <option value="Step-1_Basics.md">Step 1 - Basics</option>
              <option value="Step-2_Conditionals_Loops.md">
                Step 2 - Computed values, Conditionals & Loops
              </option>
              <option value="Step-3_Events_Data.md">
                Step 3 - Events & Data
              </option>
              <option value="Step-4_Data_Binding.md">
                Step 4 - Data Binding
              </option>
              <option value="Step-5_State_Management.md">
                Step 5 - State Management
              </option>
              <option value="Step-6_Routing.md">Step 6 - Routing</option>
              <option value="Step-7_Next_Level.md">Step 7 - Next Level</option>
              <option value="Step-8_Offline_Workshop_Version.md">
                Step 8 - Offline Workshop Version
              </option>
            </select>
          </div>
        </div>
      </div>
    </center>

    <div class="content">
      <div class="inner">
        <div ref="stepScroller" class="scrollable">
          <Step class="CurrentStep" :value="currentStep" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Step from "./Step";

export default {
  name: "Steps",
  data() {
    return {
      currentStep: "Step-0_Welcome_Goal.md",
    };
  },
  components: {
    Step,
  },
  methods: {
    stepChange: function () {
      this.$refs.stepScroller.scrollTop = 0;
    },
  },
};
</script>

<style>
.CurrentStep {
  position: relative;
  text-align: left;
}

.StepSelector > label {
  font-weight: bolder;
  font-size: 18pt;
  margin-right: 25px;
  width: 100%;
  text-align: center;
}

.StepSelector > select {
  color: var(--bloemertdark-color);
  font-weight: bolder;
  font-size: 18pt;
}
</style>
