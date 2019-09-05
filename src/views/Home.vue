<template>
  <section class="hero is-bold is-fullheight-with-navbar">
    <!--    Hero head-->
    <div class="hero-head">
      <b-navbar>
        <template slot="brand">
          <b-navbar-item>
            INVESTOR APP
          </b-navbar-item>
        </template>

        <template slot="end">
          <b-navbar-item>About</b-navbar-item>
        </template>
      </b-navbar>
    </div>

    <div class="hero-body" style="padding: 0 1.5rem;">
      <div class="container">
        <div class="columns">
          <!--Investment form-->
          <div
            class="column is-5 has-text-left"
            style="padding-right: 40px; border-right: 1px solid #dbdbdb"
          >
            <div class="block">
              <b-field label="How much would you like to invest?" expanded="">
                <b-input
                  v-model="investment.amount"
                  placeholder="Amount"
                ></b-input>
              </b-field>
              <b-field>
                <b-slider
                  v-model="investment.amount"
                  :min="10000"
                  :max="100000"
                  :step="10000"
                  ticks
                ></b-slider>
              </b-field>
            </div>

            <div class="block">
              <b-field label="For how long?" expanded="">
                <b-input v-model="investment.time" placeholder="Time"></b-input>
              </b-field>
              <b-field>
                <b-slider v-model="investment.time"> </b-slider>
              </b-field>
            </div>

            <div class="block">
              <b-field
                label="Which investment option would you like?"
                expanded=""
              >
                <b-select
                  v-model="investment.options"
                  expanded
                  placeholder="Select option"
                >
                  <option>All</option>
                  <option>Bonds</option>
                  <option>Money Markets</option>
                  <option>Equity Funds</option>
                  <option>Yield Funds</option>
                  <option>Shares</option>
                </b-select>
              </b-field>
            </div>

            <div class="block">
              <b-radio v-model="investment.term" native-value="Long Term">
                Long Term
              </b-radio>
              <b-radio v-model="investment.term" native-value="Short Term">
                Short Term
              </b-radio>
            </div>

            <div class="block">
              <b-field>
                <b-button
                  size="is-medium"
                  type="is-primary"
                  class="is-fullwidth"
                  >Calculate</b-button
                >
              </b-field>
            </div>
          </div>

          <!--Investment options Cards-->
          <div class="column is-7" style="padding-left: 40px">
            <div class="columns">
              <div class="column is-half">
                <div class="card">
                  <div class="card-content">
                    <div class="content has-text-left">
                      <h3 class="has-link">Sanlam Investment</h3>
                      <p>
                        KES 10,000.00<br />
                        Money market Funds
                      </p>
                    </div>
                  </div>
                  <footer class="card-footer">
                    <a href="#" class="card-footer-item">More details</a>
                    <a href="#" class="card-footer-item">Invest now</a>
                  </footer>
                </div>
              </div>

              <div class="column is-half">
                <div class="card">
                  <div class="card-content">
                    <div class="content has-text-left">
                      <h3 class="has-link">Government Bonds</h3>
                      <p>
                        KES 10,000.00<br />
                        Money market Funds
                      </p>
                    </div>
                  </div>
                  <footer class="card-footer">
                    <a href="#" class="card-footer-item">More details</a>
                    <a href="#" class="card-footer-item">Invest now</a>
                  </footer>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
// @ is an alias to /src

import BField from "buefy/src/components/field/Field";
import BInput from "buefy/src/components/input/Input";
import BSelect from "buefy/src/components/select/Select";
import BButton from "buefy/src/components/button/Button";
import BNavbar from "buefy/src/components/navbar/Navbar";
import BNavbarItem from "buefy/src/components/navbar/NavbarItem";
import BRadio from "buefy/src/components/radio/Radio";
export default {
  name: "home",
  components: {
    BRadio,
    BNavbarItem,
    BNavbar,
    BButton,
    BSelect,
    BInput,
    BField
  },
  data: function() {
    return {
      investment: {
        amount: 0,
        time: 0,
        options: "",
        term: []
      }
    };
  }
};
</script>
