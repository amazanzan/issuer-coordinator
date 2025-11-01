# Digit.ink Notes

This fork was originally created from https://github.com/digitalcredentials/issuer-coordinator to adjust Express request size limits (`express.json()` etc.)  

### Notes

– The `v1-0-0-modified` branch for issuer-coordinator is based on v1.0.0 of upstream due to later versions doing JSON-LD validation that requires @context to be an array of strings (which requires hosted @context, which seems to have complicated and unclear additional rules for JSON-LD validation). For signing-service we use the `main` branch but modify it too.  
– Note that the Docker version of this repo uses .coordinator.env and .signing-service.env but when using these repos directly, use each repo's .env file instead.  

### Installation

– Run `npm i` then `npm run dev`  
– Now test. After you launch issuer-coord, if you issue more than one OBV3 simultaneously, you’ll get a “tenant doesn’t exist” error for some (all but one?) of the OBV3s from signing-service. This should only happen once; issuing again should resolve the problem.  