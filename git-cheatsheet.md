Common commands:

    git checkout -b
    git push -u origin (initial push)
    git pull --rebase origin master
    git commit --amend

Delete local:

    git branch -d <branch_name>
    git branch -D <branch_name>

Delete remote:

    git push origin --delete <branch_name>

Undo:
    `git reflog`
    `git reset --hard HEAD@{2}`

Git workflow

    Checkout master branch
        git checkout master
    Pull the latest version of the master branch
        git pull
    Create new branch from the master branch
        For new feature:
        git checkout -b feature/
        For fixing bug:
        git checkout -b bugfix/
    Coding and commit new code (follow the best practice for commit message https://cbea.ms/git-commit/)
    Push the branch to the server
    Create pull request for merging into the master branch

Merge Request Note

    Một Merge Request (MR) chỉ nên có từ 1 đến 2 commits mô tả chính đến feature mình làm thôi
    Trong quá trình làm nếu commit nhiều lần thì có thể xài git commit --amend để merge changes vô commit trước đó
    Trường hợp lỡ làm quá nhiều commit rồi thì có thể tìm hiểu squash commit lại https://www.freecodecamp.org/news/git-squash-commits/ (chức năng squash này hiện Gitlab có hỗ trợ nên lúc merge có thể xài, tuy nhiên nên rèn luyện best practice trước khi tạo Merge Request)
    Prefer rebase lại branch master git pull --rebase origin master hơn là merge branch master vào lại branch của mình (như vậy sẽ tạo một merge commit mới nhìn lịch sử git log khó khăn hơn)
    Trước khi tạo MR thì chạy npm run build xem có lỗi không vì nhiều trường hợp code vẫn chạy được nhưng build thì bị lỗi

Nguyên tắc gọi API backend từ web app

    Mình thống nhất là gọi api backend sẽ thông qua layer api-services ở trên
    Layer api services chỉ import được vào server component (best practice là gọi fetch data ở server component)
    Trường hợp cần gọi API ở client component thì mình sẽ tạo server actions, rồi từ server actions đó sẽ gọi api-services nhé mọi người

Fun font: Operator Mono
