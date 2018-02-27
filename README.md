# IntlTelInput
基于VUE的国际号码输入插件
## 调用方法DEMO
```
import intlTelInput from '../intlTelInput/index.vue'
export default {
    name: 'Reg',
    components: {
      intlTelInput
    },
    data () {
      return {
        formData: {
          'agree': true
        },
        errorMsg: '',
        actForm: 'email',
        countryCode: 'tr',
        dialCode: '90',
        phoneIpt: '',
        showCount: 0,
        submiting: false,
        err_notice: ''
      }
    },
    methods: {
      setCountryCode: function (item) {
        this.phoneIpt = item.phoneFormat
      },
      setCountryCode: function (item) {
        this.phoneIpt = item.phoneFormat
      },
      tabForm: function (_tab) {
        this.actForm = _tab
        this.formData = {'agree': true}
        if (_tab == 'phone') {
          this.$http.get('https://ipinfo.io')
            .then(response => {
              if (response.status == 200) {
                this.$nextTick(function () {
                  this.countryCode = response.data && response.data.country ? response.data.country.toLowerCase() : 'tr'
                })
              }
            })
        }
      }
    }
```
