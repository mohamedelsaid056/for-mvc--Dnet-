




# ال Controllers & IActionResult 
#
ال doc مفيده جدا جدا اقراها يا ريت  [Handle requests with controllers in ASP.NET Core MVC](https://learn.microsoft.com/en-us/aspnet/core/mvc/controllers/actions?view=aspnetcore-7.0)

## ال Controllers
- عباره عن class ال method بتاعتها تمسي ال action وال action هنا هانعتبرها مجازا endpoint هايحصل ازاي؟ هاتفهم الموضوع في binding وازاي بيحصل
- بما ان اال action هو endpoint يعني محتاج حاجتين url و ايه الي هايحصل لما اضغط اوصل ل url يعني وظيفه ال Action وبيتم عن طريق اننا بنعمل implemention للي احنا عاوزينه
- ده يعتبر ال 𝗹𝗮𝘆𝗲𝗿 الوسطيه ما بين 𝗺𝗼𝗱𝗲𝗹𝘀 الي فيها [entities و كمان bussiness loiges و DBcontext الي هايحصل عليه migration ] و layer الي بتمثل ال 𝗽𝗿𝗲𝘀𝗲𝗻𝘁𝗮𝘁𝗶𝗼𝗻 𝗹𝗮𝘆𝗲𝗿 الي اسمها في mvc ال 𝘃𝗶𝗲𝘄 




<div align="center">
<img src="https://github.com/mohamedelsaid056/for-mvc--Dnet-/blob/main/2022-10-21_17-45-10-d86afecd66dd18a6f147c81b3975b8d4.png" alt="" width="700" />
  
</div>
<br>
<br>

<div align="center"> 
 -------------------------------
</div>
<br>
<br>

    
<img align="left" width="600" src="https://github.com/mohamedelsaid056/for-mvc--Dnet-/assets/138726588/025360c6-0f48-4d2e-97a0-bc68689d275f" />


##  افكرك مره تانيه بموضوع ترتيب ال middleware لانه في الاساس pipeline والترتيب مهم وان app.Run لازم تكون اخر حاجه ومن غيرها هايحصل exception لان دي الي هاتعمل short-circuiting للكل

<br>
<br>
<br>


## وظيفه ال Controllers
#### 1- بيقرا ال request 
بالي فيه من المعلومات زي ال query string و request body وrequest cookies و request header 
#### 2-عمليه ال validation  
وده موضوع لوحده 
#### 3- جوه ال action  هانعمل invoke ل model والموضوع ده مش بصوره دقيقه لان في حاجه اسمها Services هي الي هانشتغل بيها 
#### 4 - من خلاله بقدر ارجع ملعومات زي زي صفحات html او files ...div
<div align="center"> 
 -------------------------------
</div>



هاتقابل وانت بذاكر موضوع ال json يا ريت لو ماتعرفوش قبل كده تبص علي الليك ده 

[شرح json](https://www.youtube.com/playlist?list=PLHIfW1KZRIflA5jVQbAAHVizSxoeOAtgq)

### تراجع كويس الفرق ما بين ال inhertace و interface في cSharpe لان هايتبني عليهم فهم كتير  


### حاله انك عاوز ترجع من Action file في عندك 3 انواع
حاله `VirtualFileResult` ودي هاتكون في حاله ان ال media عندك في wwwroot 

```
return File("file relative path", "content type");
```
حاله `PhysicalFileResult` ودي هاتكون في حاله ان ال media عندك في علي الجهاز مثلا  

```
return PhysicalFile("file absolute path", "content type");
```
حاله `FileContentResult` ودي هاتكون في حاله ان ال media هاتجيبها مثلا من database وهاتجيبها في صوره  byte[ ] 

```
return File(byte_array, "content type");
```
يا ريت تكون فاكر ال state code من http وايه الفرق بين ال 301 و 302 و 404 و 400 و 401 وركز علي 301 و 302 لان يالفرق الي ما بينهم كبير 

في حاله ال Statecode 
 ال code 400 بيعبر عن `Bad Request` يعني في مشكله في validation 
 ```
return BadRequest();

```
ال code 404 بيعبر عن `NotFound` يعني في مشكله في بعض المعلومات من الناقصه عن server 
 ```
return NotFound();

```
ال code 400 بيعبر عن `Unauthorizied` يعني في مشكله  في ال user معندهوش صلاحيه 
 ```
return Unauthorized();

```
 
 














