<template>
  <c-stack spacing="5">
    <c-form-control is-required>
      <c-form-label font-size="lg" font-weight="bold" for="ftitle">
        Title
      </c-form-label>
      <c-input id="ftitle" focus-border-color="purple.300" placeholder="e.g. Front End Engineer" />
    </c-form-control>

    <c-form-control is-required>
      <c-form-label font-size="lg" font-weight="bold" for="fcompany">
        Company name
      </c-form-label>
      <c-input id="fcompany" focus-border-color="purple.300" placeholder="e.g. My Awesome Company" />
    </c-form-control>

    <c-form-control is-required>
      <c-form-label font-size="lg" font-weight="bold" for="fsize">
        Company size
      </c-form-label>
      <c-radio-group id="fsize">
        <c-radio value="1">
          1 - 5 people
        </c-radio>
        <c-radio value="2">
          5 - 15 people
        </c-radio>
        <c-radio value="3">
          15 - 50 people
        </c-radio>
      </c-radio-group>
    </c-form-control>

    <c-form-control is-required>
      <c-form-label font-size="lg" font-weight="bold" for="fcompany">
        Remote / On-site
      </c-form-label>
      <c-radio-group id="fsize">
        <c-radio value="remote">
          Remote
        </c-radio>
        <c-radio value="onsite">
          Onsite
        </c-radio>
      </c-radio-group>
    </c-form-control>

    <c-form-control is-required>
      <c-form-label font-size="lg" font-weight="bold" for="fdescription">
        Description
      </c-form-label>
      <c-textarea id="fdescription" focus-border-color="purple.300" placeholder="This job is awesome becasue ..." />
    </c-form-control>

    <c-form-control is-required>
      <c-form-label font-size="lg" font-weight="bold" for="flocation">
        Location
      </c-form-label>
      <c-input id="flocation" focus-border-color="purple.300" placeholder="e.g. Lusaka" />
    </c-form-control>

    <c-form-control is-required>
      <c-form-label font-size="lg" font-weight="bold" for="fsalary">
        Salary
      </c-form-label>
      <c-number-input id="fsalary" :step="1000" :default-value="15000" :min="10000">
        <c-number-input-field focus-border-color="purple.300" />
        <c-number-input-stepper>
          <c-number-increment-stepper />
          <c-number-decrement-stepper />
        </c-number-input-stepper>
      </c-number-input>
    </c-form-control>
  </c-stack>
</template>
