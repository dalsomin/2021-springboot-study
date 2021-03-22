

@Controller

@RequestMapping("/member/*")

public class MemberController

{

 ... 중 략 ...

​	@RequestMapping(value = "/info", method=RequestMethod.GET)

​	public void show(@RequestParam("seq") int seq, @ModelAttribute("myMEM") MemberInfo info, Model model)

​	{

​		logger.info("####### info.getName() "+info.getName());

​		logger.info("####### info.getAge() "+info.getAge());



​		try {	

​			//service.read(seq)가 MemberVO 객체를 반환한다고 할 경우

​			model.addAttribute(service.read(seq));

​		}catch(Exception e) {

​			e.printStackTrace();

​		}

​	}

 ... 후 략 ...

}
