# auto-curd

## text input

```
 {
            label: "Full Name",
            type: "text",
            placeholder: "Enter Your Full Name",
            required: true,
            errorMessage: "Full Name is required",
            className: "border-0",
            defaultValue: "",
            name: "fullName"
        }
```
## select 

```
    const [selectOption, setSelectOption] = useState('')


 {
            label: "Select Choice",
            type: "select",
            options: [
                { value: 'chocolate', label: 'Chocolate' },
                { value: 'strawberry', label: 'Strawberry' },
                { value: 'vanilla', label: 'Vanilla' }
            ],
            state: selectOption,
            stateFn: setSelectOption,
            required: false,
            errorMessage: "Phone Number is required",
            name: "slectChocoloate"
        }
```


## date 

```
    const [startDate, setStartDate] = useState(new Date());
  {
            label: "birthday",
            type: "date",
            placeholder: "Birthday",
            required: false,
            state: startDate,
            stateFn: setStartDate,
            errorMessage: "birthday is require",
            class: "border-2 border-red-500",
            defaultValue: "",
            name: "birthday"
        },
```


## rich text

```
    const [richText, setValueOfRichText] = useState("");


{
            label: "Description",
            type: "textBox",
            state: richText,
            stateFn: setValueOfRichText,
            placeholder: "Enter Your Phone Number",
            required: true,
            errorMessage: "Phone Number is required",
            className: "border-0",
            name: "phoneNumber"
        },
```

## image upload

```
    const [imageUrl, setImageUrl] = useState()

{
            label: "Product Image",
            type: "file",
            required: true,
            state: imageUrl,
            stateFn: setImageUrl,
            errorMessage: "",
            name: "image"
        },

```




# form code

```
 <form onSubmit={handleSubmit(onSubmit)}>
                    <div className="grid lg:grid-cols-2 grid-cols-1 gap-2 md:gap-5">
                        {formFormat.map((field, index) => (
                            <div key={index} className="">
                                {field.type === 'file' ? (
                                    <SingleImageUpload {...{ field, imageUrl: field.state, setImageUrl: field.stateFn }} />
                                ) :
                                    field.type === "select" ? <CustomSelect defaultValue={field.state} getValueFunction={field.stateFn} options={field} />
                                        : field.type === "date" ? <CustomInputDate {...{ startDate, setStartDate, field }} />
                                            :
                                            field.type === "textBox" ?
                                                <CustomRichText {...{ field, richText: field.state, setValueOfRichText: stateFn }} /> :
                                                (
                                                    <CustomInput {...{ field, register, errors }} />
                                                )}


                            </div>
                        ))}
                    </div>



                    <button type='submit' class="contactButton flex items-center bg-primary text-white font-medium py-1 mt-5 px-4 rounded-md shadow-md transition-transform  transform hover:translate-x-0.5 hover:translate-y-0.5 active:translate-x-0.2 active:translate-y-0.2 hover:text-gray-800 duration-200">
                        <div className='px-3'> Submit</div>
                        <div class="iconButton ml-4 relative flex items-center justify-center h-10 w-10 rounded-full shadow-md">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24" class="text-current"><path fill="none" d="M0 0h24v24H0z"></path><path fill="currentColor" d="M16.172 11l-5.364-5.364 1.414-1.414L20 12l-7.778 7.778-1.414-1.414L16.172 13H4v-2z"></path></svg>
                        </div>
                    </button>




                </form>
```



