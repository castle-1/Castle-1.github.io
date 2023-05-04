# Branch

- `git branch`
    - 현재 `branch`를 확인할 수있다.
      ![git branch](/assets/images/git_github_img/git_branch.png)
- `git branch -r`
    -모트 저장소에 있는 브랜치 목록을 보여주는 Git 명령어
     ![git branch -r](/assets/images/git_github_img/git_branch -r.png)
- `git branch 브랜치할 파일명`
    ![git branch](/assets/images/git_github_img/git_branch_add.png)
- `git branch switch 브랜치한 파일명`
    - 브랜치한 파일로 이동
    ![git branch](/assets/images/git_github_img/git_branch_switch.png)
- `git branch -D 브랜치파일명`
    - 브렌치 삭제
- `git push origin 브렌치파이명`
    - push 후에 github에서 확인가능
- `git merge 브렌치파일명`

# Revert

### Rename
- `mv add.py mul.py`
    - 위 방법은 좋지않다. 지우고 새로만들기 때문에 파일의 history가 남지않는다.

- `git mv add.py mul.py`
    - 위 방법으로 해야 history가 남는다.

- `git rest HEAD {filename}`
    - git에서 변경 내용을 취소하고 이전 커밋 상태로 돌아가는 기능.
    - 로컬 브랜치의 커밋을 취소하고 이전 커밋 상태로 되돌리는 데 사용.

- `git -rm -f {filename}`
    - 파일을 삭제하는 명령어
    - 이 명령어를 실행하면 Git이 해당 파일을 추적하지 않게 된다.

- `git commit --amend`
    - 가장 최근에 커밋한 내용을 수정할 때 사용합니다. 
    - 이 명령어를 실행하면 현재 변경 내용을 가장 최근 커밋에 추가하고, 커밋 메시지를 수정할 수 있다. 
    - 이렇게 하면 이전 커밋과 병합하지 않고 이전 커밋을 대체하는 새로운 커밋이 생성된다. 
    - 주의해야 할 점은 이 명령어를 사용한 후에는 push를 하면 안된다는 것이다. 
    - 이유는 이미 push된 커밋을 다시 수정한 것이기 때문에 push할 때 충돌이 발생하기 때문이다. 따라서 이 명령어는 로컬 저장소에서만 사용하는 것이 좋다.

- `git rebase -i <commit>`
    - 인터랙티브 리베이스(interactive rebase) 명령어. 
    - 이 명령어를 실행하면 해당 커밋 이후의 커밋들을 수정, 삭제, 재배치 등 다양한 작업을 할 수 있다.
    - 일반적으로 이 명령어는 커밋을 합치거나, 커밋 메시지를 수정하거나, 불필요한 커밋을 삭제하는 등의 작업에 사용된다. 
    - 예를 들어, 여러 개의 작은 커밋을 하나로 합치거나, 오타나 문법 오류를 수정한 후 다시 커밋할 때 유용하게 사용할 수 있다.
    - 이 명령어를 사용하면 수정할 커밋을 선택할 수 있고, 선택한 커밋들에 대해 수정할 내용을 입력하고 저장할 수 있다.
    - 저장한 후에는 수정한 커밋들이 새로운 커밋으로 대체된다. 이를 통해 더 깨끗하고 의미 있는 커밋 히스토리를 유지할 수 있다.

- `git rebase --abort`
    - 현재 진행 중인 rebase 작업을 취소하는 기능. 
    - rebase를 진행하는 도중 충돌이 발생하거나 다른 이유로 rebase를 중단하고 원래의 상태로 돌아가고 싶을 때 사용할 수 있다. 
    - rebase 작업을 취소하면 rebase 전 상태로 돌아가게 된다.

### Complete rebase

- `git rebase --continue`
    - git rebase 과정에서 충돌이 해결된 파일을 다시 커밋하고, 다음 패치를 적용하여 충돌을 해결하는 등 rebase 과정을 이어나가는 기능이다. 
    - 만약 rebase 과정에서 conflict가 발생하면 충돌을 해결하고 git add 명령어를 통해 인덱스에 추가한 후 
    git rebase --continue를 실행하여 계속 진행한다. 
    - 만약 rebase를 중단하고 이전 상태로 되돌리고 싶다면 git rebase --abort 명령어를 사용한다.


### Reset commit

#### Worst Case
> 직전 3개의 commit을 삭제한 후, remote에 강제 push
>> git reset --hard HEAD~3<br>git push -f origin <branch>

- 협업 시 다른 cloned repo에 존재하던 commit log로 인해 파일이 살아나거나, 과거 이 력이 깔끔히 사라져 commit log tracking이 힘들어짐.
- solution: 잘못한 이력도 commit으로 남겨두고 수정한 이력을 남기자!

#### Best Case
>현재 HEAD에서 직전의 3개의 commit을 순서대로 거슬러 올라가 해당 내역에 대해 commit, push 수행 ()
>>git revert --no-commit HEAD~3..<br>git commit<br>git push origin <branch>

- 잘못하기 전 과거로 돌아가 최신을 유지하면서 되돌렸다는 이력을 commit으로 남겨 모 든 팀원이 이 사항을 공유하고 주지시킬 수 있음.
- commit을 따로 안할땐 --no-edit
- merge commit을 되돌릴 땐 -m ( $git revert -m {1 or 2} {merge commit id} )
  
  <P style ="vertical-align: bottom; text-align: right;">출처:[yeardream]최우영 강사님 강의자료 </p>
