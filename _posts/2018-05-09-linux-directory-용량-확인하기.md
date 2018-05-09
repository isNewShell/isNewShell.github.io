---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Linux 용량 확인하기 (df, du, ls  명령어)

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
# description: >
#  jekyll 을 이용한 gitblog 만들기

# (Optional) Link to an image that represents your blog post.
# The aspect ratio should be ~16:9.
image: /assets/img/default.jpg

# You can hide the description and/or image from the output
# (only visible to search engines) by setting:
# hide_description: true
# hide_image: true

# (Optional) Each post can have zero or more categories, and zero or more tags.
# The difference is that categories will be part of the URL, while tags will not.
# E.g. the URL of this post is <site.baseurl>/hydejack/2017/11/23/example-content/
categories: [개발 이야기]
tags: [Linux]
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---
linux 환경에서 작업을 하다보면 어느 디렉토리의 용량이 큰지 확인해야할 때가 있습니다.

이럴 때 유용하게 사용할 수 있는 명령어를 소개합니다.

## 디스크 사용량 확인 - df

```df``` 명령어는 디스크 사용량을 출력해주는 명령어 입니다.
전체 디스크 중 어느 디스크가 용량을 가장 많이 사용하고 있는지 확인할 때 좋습니다.
```-h``` 옵션을 붙이면 파일 용량의 단위를 읽기 좋게 변경합니다.

```bash
$ df -h
```


## 디렉토리 용량 확인 - du

```du``` 명령어는 명시한 디렉토리 경로의 모든 하위 디렉토리 용량을 출력합니다.

```bash
$ du ./
```


## 디렉토리 안의 파일 용량 확인 - ls

```ls``` 명령어는 디렉토리 안 파일들의 정보를 출력해주는 명령어입니다.


```bash
$ ls -lhS
```

위 명령어는 모든 파일에 대한 자세한 정보를 출력하고(```-l```옵션), 파일 용량이 큰 순서대로(```-S```옵션) 정렬한 결과를 출력합니다. 그리고 파일의 용량을 사람이 읽기 쉬운 단위로 출력해줍니다. (```-h```옵션)


## 응용

현재 경로에서 용량이 큰 상위 10개의 하위 디렉토리를 확인하려면 어떻게 해야할까요?

다음과 같이 기본 명령어를 조합하면 간단하게 출력할 수 있습니다.

```bash
$ du -h ./ | sort -rh | head -n 10
```
