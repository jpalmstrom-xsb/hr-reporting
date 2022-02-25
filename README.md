# HR-Reporting

## Description
This is a Vue.2 project that allows for employee feedback to XS Brokers Human Resources. This app uses EmailJS to send an email with Templated Data. See page Form.vue to change the template data.


### Dependencies
[EmailJS](https://www.emailjs.com/docs/sdk/installation/)

[Vuetify](https://vuetifyjs.com/en/getting-started/installation/)

# Production Instructions

### Running Docker
```
docker build -t hr-feedback
```
```
docker run -dp 8080:80 hr-feedback
```
# Development Instructions
### Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
