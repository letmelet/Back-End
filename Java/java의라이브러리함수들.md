#java의 라이브러리 함수들

~~~

	public static void main(String[] args) {
		String s = "Hello Java";
		System.out.println(s.length());

		// charAt() s문자열의 n번째 단어
		char ch = s.charAt(0);
		System.out.println(ch);

		System.out.println();
		// startsWith(),endsWith() 양 끝자리 문자 확인하기
		System.out.println(s.startsWith("He"));
		System.out.println(s.endsWith(".exe"));

		System.out.println();
		// equalsIgnoreCase() 대,소문자 무시하기
		System.out.println(s.equals("HELLO"));
		System.out.println(s.equalsIgnoreCase("HELLO"));

		System.out.println();
		// substring(,) 문자열 자르기
		System.out.println(s.substring(1));
		System.out.println(s.substring(1, 3));

		System.out.println();
		// contains() 문자열 포함하는지 확인
		System.out.println(s.contains("ell"));

		System.out.println();
		// indexOf(,) "l"인덱스의 위치 확인, 같은 문자가 있을 시, 맨 앞부터 찾음
		System.out.println(s.indexOf("l"));
		// "a"인덱스를 8부터 찾아라
		System.out.println(s.indexOf("a", 8));
		System.out.println(s.lastIndexOf("a"));
		System.out.println(s.lastIndexOf("a", 8));

		System.out.println();
		// replace(,) 문자열에서 문자를 찾아서 바꾸기
		s = "1a23가4bcd나33949c다deef8라992";
		for (int i = 0; i < 10; i++)
			s = s.replace(i + "", "*");
		System.out.println(s);

		System.out.println();
		// replaceAll(,) 정규표현식을 이용하여 해당하는 모든 문자 바꾸기
		s = "1a23가4bcd나33949c다deef8라992";
		s = s.replaceAll("[0-9]", "*");
		System.out.println(s);

		System.out.println();
		// split() 정규표현식에 포함되는 문자를 사용할 때는 \\를 붙여주기
		s = "홍길동:22:hong@a.com:서울 특별시";
		String arr[] = s.split("\\?");
		for (String val : arr)
			System.out.println(val);

		System.out.println();
		// trim() 앞뒤 공백제거 (사이사이의 공백은 제거가 안됨!)
		s = "      H e l l o      ";
		s = s.trim();
		System.out.println(s);

		System.out.println();
		// toCharArray() 문자열을 문자배열로 옮기기
		char arr1[] = s.toCharArray();
		System.out.println(Arrays.toString(arr1));

		System.out.println();
		// valueOf() 모든 것을 문자로 표현
		s = 100 + "";
		s = String.valueOf(100);
		System.out.println(s);
		s = String.valueOf(1.1);
		System.out.println(s);
		s = String.valueOf(false);
		System.out.println(s);
		s = String.valueOf('a');
		System.out.println(s);

		System.out.println();
		//String.format()	같은 형태의 출력을 할 때 편하게 사용
		String name = "홍길동";
		int age = 22;
		String addr = "서울 특별시";
		String email = "hong@a.com";
		System.out.printf("%s님의 나이는 %d이고 주소는 %s 이메일은 %s입니다.\n", name, age, addr, email);

		String str = String.format("%s님의 나이는 %d이고 주소는 %s 이메일은 %s입니다.", name, age, addr, email);
		System.out.println(str);
		
		System.out.println();
		//StringBuffer()	같은 형태의 출력을 할 때 편하게 사용
		StringBuffer sb = new StringBuffer();
		sb.append("#1 19\n");
		sb.append("#2 23\n");
		sb.append("#3 77\n");
		
		sb.insert(0,"#4 222\n"); // 0번째 추가
		//sb.delete(0, sb.length()); // 전부 비우기
		
		String s1 = sb.toString();
		System.out.println(s1);
	}

~~~
