---
title: 소스트리-깃랩 연동하기 (SSH)
author: Yongjun
date: 2020-05-10 00:00:00 +0900
categories: [git, sorcetree]
tags: [sourcetree, gitlab, ssh]
---

터미널에서 SSH 키 생성  
~~~
$ ssh-keygen -t rsa  
~~~
  
입력하면 저장경로와 비밀번호를 설정한다  
아무입력없이 엔터만 누르면 기본경로에 비밀번호없이 생성되지만 보안상 비밀번호는 설정해주도록 하자  
~~~
$ Enter file in which to save the key (/Users/계정/.ssh/id_rsa): <저장 경로>
$ Enter passphrase (empty for no passphrase): <비밀번호 입력>
$ Enter same passphrase again: <비밀번호 확인>
~~~

저장경로로 이동해서 id_rsa.pub 파일을 열고 안에 내용을 모두 복사한다  


GitLab 웹페이지에서 오른쪽상단 프로필이미지클릭 - Settings    
![settings](../../assets/img/git/settings.jpg){: width="50%"}

  
왼쪽 메뉴에서 SSH Keys - Key 필드에 id_rsa.pub 복사한 내용을 붙여넣기 - Add Key 버튼 클릭
![sshkey](../../assets/img/git/ssh_key.jpg){: width="100%"}
  
  
왼쪽 메뉴에서 Access Tokens - 이름과 권한설정 - Create personal access token 버튼 클릭
![accesstoken_1](../../assets/img/git/accesstoken_1.jpg){: width="100%"}
  
  
생성된 Access Token 복사  
![accesstoken_2](../../assets/img/git/accesstoken_2.jpg){: width="100%"}
  
  
SourceTree 실행 - 설정  
![sourcetree_settings](../../assets/img/git/sourcetree_settings.jpg){: width="50%"}
  
  
GitLab 이름과 복사한 Access Token 붙여넣기   
이름은 자신의 프로필에 적혀있는 이름(FullName)을 적어야한다 (Access Token 생성할때 입력한 이름이 아니다)  
SSH 프로토콜로 설정   
![gitlab_account](../../assets/img/git/gitlab_account_ssh.jpg){: width="70%"}
  
  
자신의 맥 계정 비밀번호 입력  
![mac_pw](../../assets/img/git/mymac_pw.jpg){: width="70%"}  
  
  
GitLab 비밀번호를 입력  
![gitlab_pw](../../assets/img/git/gitlab_pw.jpg){: width="70%"}  
    
    
이제 소스트리에서 SSH로 깃랩 프로젝트를 사용할 수 있다  
  
만약 실수로 소스트리나 키체인의 비밀번호같은정보를 잘못입력하고  
이후 잘못된입력내용이 캐시되어 계속 실패가 뜬다면  
키체인과 소스트리 계정정보를 지우고 다시 시도하면 된다  
   
소스트리 계정정보 지우기   
1. 파인더 열고 커맨드 + 시프트 + G  
2. “~/Library/Application Support/SourceTree” 입력   
3. {이름}@STAuth-gitlab.com  파일 삭제   
  
키체인 지우기   
1. 커맨드 + 스페이스   
2. “키체인 접근” 검색 - 실행    
3. gitlab 검색 - 파일 삭제   
  
