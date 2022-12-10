# C0821G1-DuongPham
# C0821G1-DuongPham
# C0821G1-DuongPham
# C0821G1-DuongPham
# C0821G1-DuongPham
let users = [
  {
    id: 1,
    name: "Kien Dam",
  },
  {
    id: 2,
    name: "Son Dang",
  },
  {
    id: 3,
    name: "Dang Dam",
  },
];

let comments = [
  {
    id: 1,
    user_id: 1,
    content: "Anh son chua ra video :(",
  },
  {
    id: 2,
    user_id: 2,
    content: "Vua ra xoong em oi!",
  },
  {
    id: 3,
    user_id: 1,
    content: "Cam on anh ^^",
  },
];

// lay comments
// tu comment lay ra user_id
// tu user_id lay ra user tuong ung

// function getComment() {
//   return new Promise((resole) => setTimeout(() => resole(comments)),1000);
// }
function getComments() {
  return new Promise(function (resolve) {
    setTimeout(function () {
      resolve(comments);
    }, 1000);
  });
}
// function getComments(){
//     return Promise.resolve(setTimeout(()=>resole.comments)),1000;
// }
getComments().then(function (comments) {
  let userIds = comments.map((comment) => comment.user_id);

  return getUsersByIds(userIds).then(function (users) {
    return {
      users: users,
      comments: comments,
    };
  });
});

function getUsersByIds(userIds) {
  return new Promise(function (resolve) {
    let result = users.filter((user) => userIds.includes(user.id));
    resolve(result);
  });
}
