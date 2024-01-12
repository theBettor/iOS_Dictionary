1. 시간순으로 main branch에 오래된 commit이 있고, develop branch에는 최신의 commit이 있다.
   develop에 있는 commit은 vi Podfile안에 ReactiveKit과 Bond를 추가하게 되면서 자동으로 xcworkspace가 생성 되어서 xcworkspace에서 작업을 하고 있다.
   다른 사람 기준으로 내 앱을 clone repo를 할 경우, 그나마 정상적인 commit이 되어있어야 할 것 같아서 main branch에 있는 오래된 commit을 merge to master를 했던 것 같다.
   그 과정중에 오래된 커밋은 xcworkspace가 당연히 생성되지 않았던 때라 해당 commmit으로 checkout 되어있는 상황에서 xcworkspace를 열면 파일,폴더 등을 확인할 수가 없었다.
   이럴때는 https://silver-g-0114.tistory.com/144 링크처럼 xcworkspace save as를 해서 기존 xcworkspace에 덮어쓰기를 하면 정상적으로 파일 등이 생성되어 있는 것을 볼 수가 있다.
