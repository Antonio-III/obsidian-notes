# Databases

relational db
	tables to save data


non-relational db
	no tables, save data in form of strings (str)

To create a table:
```sqlite
 create table students(sid int, fname char, lname char, email varchar);
 ```

`sid, fname, lname, email` are names of header rows.
`int, char, varchar` are data types. 


To insert values to a table:
```sqlite
insert into students(sid, fname, lname, email) values(1,'Jo', 'Intal', 'example@email.com');
```

Notice we use single-quotation marks to represent `char`. 

To see the inserted data:
```sqlite
select * from students;
```

Output:
```sqlite
1|Jo|Intal|example@email.com
```


# Org Intro

Our company's bussiness offers a cooking service, whereby customers will call the business owner to order some kind of food, and she makes and delivers this food to the customer. The kinds of food her business makes are typically Filipino foods with some optional baked goods. 

In the case of advertising her business, she has a pamphlet that shows the common dishes that she makes. It includes meat, vegetables, and seafood dishes, as well as bread, noodles, and cakes. As far as we know, her business doesn't have a website which significantly hinders the visibility of her service to the public eye. 

This means the only way someone can know about her business is if you know her closely or through word-of-mouth from mutual friends.

# Proposal

So our proposal was to make a static one-page website that showcases her services in a digital medium. This means that her business will have a digital footprint, so someone out there on the internet can come across her services and potentially attract new customers from there. 

# Communication

Our method of communication was primarily done through emailing and text-messaging apps. We reached out to her initially via gmail. And continued our communication through WhatsApp.


As for creating the prototypes, we used Figma to initially design the wireframes, and eventually the prototypes.

And we used Canva to create this powerpoint presentation.

# Code of Ethics for Software Engineers

The document is a compilation of 8 principles, it regards the (i) public, (ii) client and employer, (iii) product, (iv) judgement, (v) management, (vi) profession, (vii) colleagues, and (viii) self.

The document states that since computers have begun to be widely used in a variety of areas within society, the software engineers who directly participate in the creation of software systems have an influence to cause good or harm to these areas of society. Therefore, this document will serve as the founding principles that software engineers **ought**
to follow to cause as much good as possible.

The document states that it is not intended to be used to justify harm. The document states that it is not intended to separate what is necessarily acceptable and what isn't. The document states that it does not cover all possible scenarios, in which case the software engineer must use their judgement to act in a way that is the closest to what would be prescribed in this code of ethics. 


In summary, the document describes that the affected parties in the 8 principles must be held to a standard such that: 
## I. Public

The decisions about the software system must be identified and adressed to the appropriate authorites; to address the software's impacts on the majority and minority populations; and the work should be towards the good of the public. 

## II. Employers and Clients

The engineers must use software that are ethically obtained, and must be within the client's and employer's consent; address issues raised during the software's devlopment to the appropriate affected party; and to keep confidentiality when it is for the public good and consistent with the law.

## III. Product

The product delivered must be in high quality, is within a reasonable cost and schedule. Issues regarding the impact of the product must be addressed. The workers must be qualified to work for the project. And to depart from the standard only when it is morally and technically justified.

## IV. Judgement

The software engineer should only provide judgement when it is in their field of knowledge, and to be objective when evaluating work from themselves or others.

## V. Managers

The managers should promote quality and risk reduction; to communicate the standards and policies to their employees before holding them to such standards. Managers should only assign work only if the employee is resonably competent in that field. And they should only attract employees by providing accurate descriptions of the employment.


## VI. Profession

Software engineers should promote public knowledge of their profession. They shall not promote self-interests at the expense of the profession. And They shall obey laws unless it is against the public's interests.

## VII. Colleague

Software engineers shall assist colleagues with their work; to promote adherence to this code; review each other's work in an objective manner; and be fair to the complains of a colleague.

## VIII. Self

Software engineers shall deepen their understanding of this field; to improve their ability to create usable code; to not be unjustly prejudiced against someone; and to not influence other or themselves to violate any of the code.

# Assessment 2

## Technical Description

Implementing the site design based on its final prototype design relied on a strong fundamental knowledge of how layouts work in web development. One of these layouts is called `flex`. This enables the ability for a markup or HTML element to be arranged one-dimensionally. It can either make the flex items arranged horizontally or vertically. This is one of the design principles the implementation of the prototype was built upon. And it is that the elements are arranged in a one-dimensional manner.

An instance of this one-dimensional arrangement is the container for all of the site's content. The site, in its whole, is divided into four main sections. These sections contain their respective content design, and thus their own arrangement of items. But the sections are collectively arranged in such a way that they looked vertically placed on top of each other. Within each section is another container that also arranges its items one-dimensionally, either horizontally or vertically. The whole implementation of the prototype follows this pattern of arrangement.

Another procedure of the implementation is to resize images that are used in the site. In this case, the method of resizing images is the use of `max-width`. This enables images that are too big to be readjusted to fit the intended size. 

We used animations in the implementation to visually appease potential customers, and to make the aesthetics of the site more dynamic and lively. The animations were applied on a JavaScript object called `window` that calls a function upon scrolling the site. The window refers to the screen in which the JavaScript code is running, and upon scrolling through this screen, a function is called. The function itself detects if an arbitrary condition has been satisfied, which then adds a class that overwrites the `display` property of a DOM object.

Lastly, is the implementation of a chatbot for a user-interactive experience, and to potentially answer basic questions a customer may have. The chatbot itself has been programmed only to answer basic questions, like showing the menu or prices. Any topics outside the scope of its pre-defined goals will not result in any meaningful response. Adding the chatbot hasn't been difficult, as it openly supports web integration.

