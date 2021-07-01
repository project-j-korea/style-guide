# Git Style Guide

### English

#### Branch Naming

- **master :** product deploy
- **feature/#XX :** Enter the github issue number on XX, `ex) feature/#132`
- **hotfix/#XX :** Enter the github issue number on XX, `ex) feature/#132`
- **deploy/YYYY-MM-Week :** staging deploy, qa/qc `ex) deploy/2021-01-4`

#### Commit Message Writing Style

- Write a summary of the simple work in `<title>`. Less than 50 characters.
- `<title>` is written in English.
- **Add Features :** Add: `<title>`
- **Modify Features :** Fix: `<title>`

#### Gitflow Role

Project J used a strategy that integrates github-flow and git-flow.
The rules for working with you are:

1. Create Github issue

   - `Title` is written in English.
   - In `Assignees`, select an developer.
   - Select the appropriate action tag for `Label`
   - `Project` is set to `oranization/project` for each service.

2. We work without any explanatory attached to the code.
3. After Develop, On the `deploy/XX` branch, PR is created in the form `[#XX] Test Pull Request`.

   - In `Assignees`, select an developer.
   - Link the issue that matches the number.
   - You immediately Squash merge after PR. Modify the title in the merge course as `Merge [#XX] Pull Request`.

4. After testing in the `deploy/XX` branch, create PR in the form of `[#XX] Pull Request` in the `master` branch.

   - In `Assignees`, select an developer.
   - Link the issue that matches the number.
   - `Project` is set to `oranization/project` for each service.
   - squash merge after receiving the reviewers' approves. Modify the title in the merge course as `Merge [#XX] Pull Request`.

5. You are responsible for the part you worked on. In the event of an error, you have to roll back and correct it yourself.
6. If Conflict is created, the worker who deploys it later will proceed after rebase. (Make sure confilct is not modified in github)
7. In the event of an error, the develop who worked on the code generates and corrects the branch according to [Branch Naming](#Branch-Naming) after the rollback to that code.
   - PR from 'hotfix' branch to 'master' branch is the same as normal work. Instead of squash merge, commit merge.

### 한국어

#### Branch 네이밍

- **master :** product 배포
- **feature/#XX :** XX에는 github issue 번호를 입력 `ex) feature/#132`
- **hotfix/#XX :** XX에는 github issue 번호를 입력 `ex) feature/#132`
- **deploy/YYYY-MM-Week :** staging 배포, qa/qc `ex) deploy/2021-01-4`

#### Commit 메시지 작성 Style

- `<title>`에는 간단한 작업 내용을 요약해서 작성합니다. 50자 미만.
- `<title>` 영어로 작성합니다,
- **기능 추가 :** Add: `<title>`
- **기능 수정 :** Fix: `<title>`
- **기능 핫픽스 :** Hotfix: `<title>`

#### Gitflow 규칙

Project J에서는 github flow와 gitflow를 통합한 전략을 사용합니다.
작업을 하실때의 규칙은 다음과 같습니다:

1. Github issue를 생성합니다.
   - `Title`은 영어로 적습니다.
   - `Assignees`에 작업자를 선택합니다.
   - `Label에` 알맞은 작업 태그를 선택합니다.
   - `Project`는 각 서비스의 `oranization/project`로 설정합니다.
2. 코드에 주석은 일체 달지 않고 작업합니다.
3. 작업 후 `deploy/XX` branch에 PR은 `[#XX] Test Pull Request`형식으로 생성합니다.

   - `Assignees`에 작업자를 선택합니다.
   - 번호에 맞는 issue를 Link합니다.
   - PR 즉시 squash merge합니다. merge과정에서의 title은 `Merge [#XX] Pull Request`와 같게 수정합니다.

4. `deploy/XX` branch에서 테스팅이후 `master` branch에 `[#XX] Pull Request`형식으로 PR을 생성합니다.

   - `Assignees에` 작업자를 선택합니다.
   - Project는 각 서비스의 `oranization/project`로 설정합니다.
   - 번호에 맞는 issue를 Link합니다.
   - reviewer들의 approve를 받은 이후 squash merge합니다. merge과정에서의 title은 `Merge [#XX] Pull Request`와 같게 수정합니다.

5. 자신이 작업한 부분은 자신이 책임집니다. 에러 발생시 롤백 및 수정은 자신이 해야합니다.
6. Conflict가 생긴 경우 나중에 배포하는 작업자가 rebase작업을 한후 진행합니다. _(github에서 confilct를 수정하는 일이 없도록 해야합니다.)_
7. Hotfix 발생 시 에러가 발생한 코드를 작업한 작업자는 해당 코드에 대한 롤백 이후 [Branch 네이밍](#Branch-네이밍)에 따라서 브랜치 생성 후 수정합니다.
   - `hotfix` branch에서 `master` branch로 PR은 일반 작업과 똑같이 하되, squash merge대신 commit merge합니다.
