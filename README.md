#SPRING_BOOT_WEB

1,2,3,4,5,6주차 추가 예외처리까지 완료


<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <meta charset="UTF-8">
    <title>블로그 게시판</title>
    <meta content="width=device-width, initial-scale=1.0" name="viewport">
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
</head>
<body>
<div class="container">
    <h1 class="mt-5 text-danger">블로그 게시판 - 잘못된 접근</h1>

    <!-- 오류 메시지 -->
    <div class="alert alert-danger mt-4" role="alert">
        <h4 class="alert-heading">잘못된 게시판 접근입니다!</h4>
        <p>요청하신 게시글을 찾을 수 없거나, 접근 권한이 없습니다.</p>
        <hr>
        <p class="mb-0">이전 페이지로 돌아가시려면 아래 버튼을 클릭해주세요.</p>
    </div>

    <!-- 이전 페이지로 돌아가는 버튼 -->
    <div class="mt-4">
        <a href="javascript:history.back()" class="btn btn-primary">이전 페이지로</a>
    </div>
</div>
</body>
</html>

