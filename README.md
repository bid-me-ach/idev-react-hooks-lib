# Idev React Components Library

This package is for a custom react hooks, and many more....

## NPM package
[https://www.npmjs.com/package/idev-react-components-lib](https://www.npmjs.com/package/idev-react-components-lib)

## Doc

Install Package
```bash
npm i idev-react-components-lib
```
## Components List

#### 1. IdevButtons
#### 2. IdevForm
#### 3. IdevInputGroup
#### 4. IdevInputs
#### 5. IdevLabels
#### 6. IdevTextArea


## Usages


```bash
import React from "react";
import { IdevForm, IdevInputGroup, IdevInputs, IdevLabels, IdevButtons } from "idev-react-components-lib";

export default function Home() {
  const [fromData, setFormData] = React.useState({
    name: "",
    email: "",
    message: "",
  })

  const handleChange = (e: React.ChangeEvent<HTMLInputElement>) => {
    setFormData({
      ...fromData,
     [e.target.name]: e.target.value
    })
  }

  const handleSubmit = (e: React.FormEvent) => {
    e.preventDefault()
    console.log(fromData)
  }

  return (
    <main className="flex min-h-screen flex-col items-center justify-between p-24">
      <Nav listItems={menuItems} />
      <IdevForm onSubmit={handleSubmit}>
        <IdevInputGroup WrapperClass="flex flex-wrap">
          <IdevLabels className="text-left">Full Name</IdevLabels>
          <IdevInputs inputTypes={
            {
              name: 'fullName',
              type: 'text',
              value: fromData.name,
              onChange: (e) => {
                handleChange(e)
              }
            }
          }/>
        </IdevInputGroup>
        <IdevButtons className='p-5 bg-slate-400 text-white'>Hit Submit</IdevButtons>
      </IdevForm>
    </main>
  );
}
```
## License

[MIT](https://choosealicense.com/licenses/mit/)