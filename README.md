# README

This is study material for rspec testing. 

## Notes 

- TDD stands for test driven development. The idea is you write the test first, and then write the methods, etc. that you are testing for

### How to declare a test 
```
RSpec.describe User, type: :model do 
	context ‘validation tests’ do end 
		context ‘scope tests’ do end 
end 
```

### What is context? 
- context is just the "name" of the test 
- describe and conext are the same but when you want to encapsulate an idea, use conetxt (this is a convention)

### Use "let" for DRY-er code 

```
 let (:params) { {first_name: 'First', last_name: 'Last', email: 'sample@example.com'} }
    before(:each) do 
      User.new(params.merge(active: true)).save
      User.new(params.merge(active: true)).save
      User.new(params.merge(active: true)).save
      User.new(params.merge(active: false)).save
      User.new(params.merge(active: false)).save
    end
```

- instead of declaring each user individually, use let to create a set of params for the user

### What kinds of things can be tested? 

- models, views, controllers, helpers, mailers, requests, features, routing and more can be tested 

### Why is coverage important? 

- coverage lets you know how much of your application is tested for. This is important for determining how well your application will work before it goes into production. 

### Is there a gem that lets me know how much testing coverage I have? 
- Simple Cov is a way to make sure you have good coverage