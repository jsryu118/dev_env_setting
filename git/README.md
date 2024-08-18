submodule 추가 안하고 올리고 push하고 싶을 때\
rm -rf .git \

만약 이미 추가되엇다면\
git rm --cached -r folder_name


# 비밀번호 계속 안치도록
임시저장 15분   
git config --global credential.helper cache\
연장하려면\
git config credential.helper 'cache --timeout=300'

영구 저장
git config --global credential.helper store

저장된 정보 없애기
rm ~/.git-credentials
git config --global --unset credential.helper




asdfasdf
asdasdf


