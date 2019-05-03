- Single Source of Truth

### What is OpenAPI?
  - Standard structured approach for describing RestAPIs that is both human and machine readable
  - Historically known to auto generate api documenation.
  
### OpenAPI Documentation Design First
  - Consistency
  - Code-first is expensive
  - Gain fulle benefits of OpenAPI

### Mocking and Feedback
  - OpenApi document mocks the request and response
    - Prism is a mock server
    - If you use or build internal APIs(including libraries/SDKs),
      - You can
        - Build faster
        - Parallelize development
        - more options
    - If you write docs or tutorials,
        - you can
            - Start writing sooner
            - Give feedback
            - Have interactive docs
    - If you care about developer experience or advocate for users, 
        - you can
            - power feedback loops
            - put real endpoints in front of users

### Start with humans
    - Questions to ask
        - Will the API help users to achieve these tasks?
        
    - Public OpenAPI Specification Documentation

### Testing
    - Machine Readable
    - Linting
        - acts as a style guide
        - specy or spectral
    - Validation Testing
        - Dredd/spotlight/swagger
        - What is contract testing?
            - Insures the single source of truth is acurate
            - Gives *Less* broken SDKs
            - Update SDK Code
                - Open Pull Request
                - CI runs contract tests
                    - Pass or Fail

- slides noti.st/tbarn
- tools openapi.tools
