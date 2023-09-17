# Kinds

In the current protocol (`v1`) all objects (`shared keys`, `vaults`, `proposals`, ...) are encrypted using [NIP04](https://github.com/nostr-protocol/nips/blob/master/04.md).

## 9288 - Shared Key

This kind it's used to share shared keys between participants of a `vault`. 
It's used to encrypt and decrypt everything related to a `vault`.

### Required tags

* `e`: event ID of the `vault`
* `p`: public key of the user able to decrypt the content of this event

### Example 

```json
{
    "content":"PDj1bNB1PuWKzPc1RrKBmbEeXDaYkxRIsAqTraJscUq4ML3+mZzJq4O6vPkkIJeZuNQTp0EyLxAvUblXCgJxaEgwxRWQC+rpdz3ILjdQA2w=?iv=B5KnzXU7smmAWevhTi1rSg==",
    "created_at":1693903672,
    "id":"6bc1eb162aa5d0623370d808578d15a77e1e91a55ee93255ec070d5e03b4c87f",
    "kind":9288,
    "pubkey":"f831caf722214748c72db4829986bd0cbb2bb8b3aeade1c959624a52a9629046",
    "sig":"ad9bc22082b5b5d23b75bb3752109b1d6d97a7ff29f1effdc710943c69f7550479856c06e76e4361e033be7400a27a9e688b3a4cf417840b7dd2b0df1403ec39",
    "tags":[
        ["e","071dd01141b000f7d0c9f8172101e8efb5771939456d8e4a3f8b37f6d458e82d"], // Policy ID
        ["p","f831caf722214748c72db4829986bd0cbb2bb8b3aeade1c959624a52a9629046"]
    ]
}
```

## 9289 - Vault

TODO: description

### Required tags

* `p`: public keys of the users involved in the `vault`

### Example

```json
{
    "content":"uTK3M5F958K1HKEJf/8ciVNLVw0u6dwkSANxWGBkZvpM3/3kIR/miLUPGuYLskl8ttBcLRXU07fq1mhC0+PsppJo5PQ3XyWFGWGWOQXktOKPIhpQcbpX6xCZACKN9BP6x1kCt8RCJB8nwqx0mD21syZRoQdOqKXWR/1r4rqknMS4uPY3nwT15vkP0p6zP6ZD4m9ykBhiRhGiUYxdakMcKcfHt1R22OF0trCt1+KpL9cdVqHpiiJy9hofgKb7wqPFnwcoRVlariXoQIIOoZHzOS69rzmqLFAyz6PWl2ifSwhDX9VCMw6vzp8Trp0lO/txhGW6+mIn9DBebj0cJQCygUaUmpzyBXOAzuzndUDPHMsls12qeOfX64edLgGyC/jL7qG9HS6Z1Wo91jlpqwTmqY3yzMGGcMZ01VkJ0jmbB8OuuO/BfrU3YMLQMAXMyc8BVyyksNIrG9tEMJlGDe4w1Wl2Ss7jiZRqLzuJua7w0RpApAmQ8zAsaDojVOEES87/pG+Pl6EyQxnofMMmdi1A+LSBQBAjtglGdKaK740I6Cjc2acBwqohiM8CV+tbTCqn?iv=fPuKqXaCoczpZ/3eikrTbQ==",
    "created_at":1686479425,
    "id":"9e0dfd2177ea9357f0c165ed134a86a3c07449676d8315e12d159932ff428e37",
    "kind":9289,
    "pubkey":"4639e297633117888df17deed6b3860ff152e9e464690623b6b3d6ae4923ad62",
    "sig":"2ff3f48a7e80db25418df983c732edbc495b0fb28f4fdf051955867c0e180131f7f7e9499957adee76bc9fdedc5fb7c8a71ec7e1655322e39cf5d4f590bfcd15",
    "tags":[
        ["p","3eea9e831fefdaa8df35187a204d82edb589a36b170955ac5ca6b88340befaa0"],
        ["p","f831caf722214748c72db4829986bd0cbb2bb8b3aeade1c959624a52a9629046"]
    ]
}
```

## 9090 - Proposal

TODO: description

### Required tags

* `e`: event ID of the `vault`
* `p`: public keys of the users involved in the `vault`

### Example

```json
{
    "content":"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?iv=whier1QoEXYwFJhwcpcl3A==",
    "created_at":1694781913,
    "id":"726e919e26dcc70dbc3926660afa589793233ca6c94e69f9687fd03c02f74263",
    "kind":9290,
    "pubkey":"4639e297633117888df17deed6b3860ff152e9e464690623b6b3d6ae4923ad62",
    "sig":"5c88ff5bf65fe8da798bfd8303f493040055748d6c06d623b26393d78631edc0dadd79a4cd6f10930feb43d23900390c7dabbf5287c4a32b8c0970a6a3e9d0c1",
    "tags":[
        ["p","3eea9e831fefdaa8df35187a204d82edb589a36b170955ac5ca6b88340befaa0"],
        ["p","f831caf722214748c72db4829986bd0cbb2bb8b3aeade1c959624a52a9629046"],
        ["e","9e0dfd2177ea9357f0c165ed134a86a3c07449676d8315e12d159932ff428e37"] // Policy ID
    ]
}
```

## 9091 - Approval

TODO: description

### Required tags

* `e`: event ID of the `vault` and the `proposal`
* `p`: public keys of the users involved in the `vault`

### Optional tags

* `expiration`: UNIX timestamp of the expiration of the approval

### Example

```json
{
    "content":"xTv+0Vw4fzB3Kt5x6LK9rjnbIG7sL7J1J+nvoA1OmBw4ERa/8xvqQKv4DWkjDpy58cHYrtidnIcYeNsG0ATQ1p5VSlpqb4bw4RS2OpMT7MbTqS5jSTqpOTSSeu2zDc2yF0+VE3GgDydrt5ck5Hx8rdkPkAJ+rLJ4tcAUBo53gMzTBJ/wGMFTTsVK9w6nSq43ERfow3fzoxwUIru9gBbOFoYg+svqPByL/GvIuvjTPPHGzimQxdTqkkmAy+pjSTYE/UJ4rVbmuerdoQAH87cYwWmpcPaF0hbsvV2071DhMJjHFASN0L/1zjRYZheddDZNT9ePyv6tHQ4RczJF4apR8lyUEJp6wECU6/xFy5dXMn0a6VDrPFJ8s9A3dSD+6CkCI1o3wIBlixPDQUDtNN69h1ZMJhDbiirFXsAYy9nkA5LGDYhUw9mdB8NG5friFxthZW1cwWYm/uudUAreOJBtUaNqNLhwfxvgnDjDjUrgOnT+DxRllsnLoshuv0IXwcYp5dYtiD/e30lEefdeZ4CrIfQdZkndpIBfcwBJG0RUNgfOdkVgurhhxuKFp3/oHaW8X+EnIW6EQRR0ut4PQJFglQtjGJjUlZ5yb/IBGvGnVfgGXLThN0hiA5QP78CBWinkEbPL/Z0mOI6bLkVW4Zo+xt4Pntxh2k4PSO5SizuZz7EWkmTt9Jxq+597T7Io6t6m6Kx7ryURN1OPwSGEXdxyRkIOcwxOsD2RILvwxF5h/Mt/Z/oyJ0ylUTTyxkkAbzluhtjlLyC1lzmE6L0U4P9/iK/7TMequnT24Rtt44HggpYP7d9a9dasvCDiZLUvxLGnjKN7RAoxQb1j9zELOl0LKem84/e5vIIeobYaH000FYiup1imxPZJ+Ufd/K6Coxf7YQY7TCqP79xLGteM2saium8WP3IH9yd4R/g7fxFVTt37S/Ys67HHNgmDx6fzb5NOgwTs/Iz8IO4LMiXVZAoJJ5cC+6lwbgNuuSvQ50g67NdY+NLWyVofFY3TJkkx/bXeracUlJrxKJG4jYQhm41z4/UKCFnAf5uq+6aDoWUpyNu2QB4Z+6glYH5IyJz2XgbZBz1zjWb4BCc/tT17J9UCn/B1OIKLFnHl+2tLR0T8/ZN6cwRlA/o3S9vTmNbu5QtvEqXxlE+r9OasCwPXrmV2QdYw8I/h1XzbDFPK54UGJVxy1P3CM0oGtnCibaZdFyslAr/R+l79NHw64ApuEhP7ZNHTFxB2yLfMAcAYf6fuqw0YxJiV78ui1fSue4IUV6+wlPFKBfz/RqTG0zkmZId8NPiPXUCzy7wMvZwcTZFEhZOUijlxLBWMwr3tXYzJHUbWfzHrhwued68SWw0AinUeP3mkREju0uo7ja6pKKFtAhP+VzO9ZqqTA+VDAIlNmvFw4aela8MLbgNCpVDNI3wxj3fb0PpWjmETG1DrDPpkYlpBBBRemFOOhhwcLx4kjNqKr4db1cYN/A5wWe6QXOTPs9EeyrWQXGOIxNgQA0+VJJeynmXGxZ2Vsb+mhj/X7XHyVKOl4yAvx9xqe+kMsDg7Ww9bT2jiIJ0kqOjxZmusa3v/naV7rGjKRbkBE7U4xdsgfb+Z7wIBo0qkSQyMYqDt2L26Nj77pQkCjvitpm0WULl5hTJMCnTxtE8io/C3TsVQ1PaKWYNAJi9W/OcOmgPH1gq+EKmgrgi1sfUk2KXEVALQWncbSZtBAqMLtsH3R0+I//03VbeMFFvWXi7yDfVBE5iCUPcVpPFYSsrTdCHu6f5QMTukIn2xplKsAK6tk7hMfZ+3u9yzlC3M1GCe7PSm+tLlYSOxkB1smmWn/ZLF1dYuoAyGbwGG+wL2J+GpjOO0u5LqZpO202CVhT9hZ178HjvDMYVqR7SIfnVR4mAIkvfvnoMYTJBEKjT9fKJNJCgi?iv=3uD9CK7zc9OTGN8VGyKqtw==",
    "created_at":1694703253,
    "id":"728e7aa746d4c207f118576d41908e92788616b86ae9108d3249fced0023168b",
    "kind":9291,
    "pubkey":"f831caf722214748c72db4829986bd0cbb2bb8b3aeade1c959624a52a9629046",
    "sig":"7d6219e097559ad0b3ac8a5e7529a4f709cf0701d2003cc8ecacb829a3db723c819a0254b012faaddfd67ce690a7437c8cec01c90f94cf76472919e8a31a85ba",
    "tags":[
        ["p","3eea9e831fefdaa8df35187a204d82edb589a36b170955ac5ca6b88340befaa0"],
        ["p","f831caf722214748c72db4829986bd0cbb2bb8b3aeade1c959624a52a9629046"],
        ["e","e64282e3491ebf5de5ca499bd211d5a26d1636d3197f7341d6eef804ed0a61b0"], // Proposal ID
        ["e","9e0dfd2177ea9357f0c165ed134a86a3c07449676d8315e12d159932ff428e37"], // Policy ID
        ["expiration","1695308053"]
    ]
}
```

## 9092 - Completed proposal

TODO: description

### Required tags

* `e`: event ID of the `vault` and the `proposal`
* `p`: public keys of the users involved in the `vault`

### Example

```json
{
    "content":"vMg2YFd3xXhNbLt+IK81FoBfvztBSLjEEiXzeTrYDrhOGmjhmNorLCl8JsRdjjMl1mULdX6UGmu1bQq3EY2v/HNLiiHfb/TU1LhD+XOXvRBUCQToEguarQcknVqVSry7GzIH+J0z6aT/DbYzMpWeA3g6q3HMBs6sj5QfBb6DokUKbFadq74CDnHoEgQ9qhcJaL3qZXL5g01J47u1ceHW+G6/iTEH+TFBKw4iQhdzFH+GyMugow3EmSvuPiiVFr+ZI6iAo14DqqjKKC41XW5wnFeZ2TZTbTHDqnTQrguvfULCpP7p7yOFKlnTUzd0Mgw41xB7FUFCkAmIpZaMNQErCIp0/PTtBZheUM9GHFvuJO3gmZ2B4b4HlbFEpNQ5S8+aYxIOaawLYKbdV7CNjE/hwB2ZQbDLB/UcQ8mbYzkEh6z2bARTCKoiqpNhIyj+OjZbkYjFm/J0ZDAOc8kSyuSqOXGyrtbL669ZBSRXxDkagBmX2lFJ3FZmDsWUbWDtY6IZsCIZDwncVH/P+hU1zUAh+vvdHtt4TSJ+4Iclg1sv9c/Rd/esgjlh4SMav/HBsjkGeaiifRP+rDq5JYRJZi+7xkna9vak1ClBBJL6NUpx87a3h3D95XcRBQQidJhCAMk0Smil5IOB7iz1H71SsJ88+mVNvw0S6Nxy2qfA3FU9j4Kz7X5+F74dHy4UHbn9GCCjNNCQXyZ8S1A/WtQQCv89Gnv99QcX6wkZtVpJ8dLsGUBzZ78xYkfjagzfj2idAxrlCTWmn7fdkc4ZWEzr6JE7GOnLyrjerfVZzecp5kuTM+7j170rLGgnOpt68MSTC7q68M3AwLW9/0s5iC5tMmZJuLnUvMg6A2ZSLr3IaDIazOgH3EbK3RsZ4AUwTRwiCYwu7LQTsiRMvAIG0wrfe3Ldb9G9qHyo5KgNr1CAb7upip0/HL04aNJISn5qEO/cCNM0nW2S41h+Xr9p6NDngnNPnLXC/r+Y1wSEt2bHuemlzC+BUZxsFG300bEpQMsiYJQFmj2JezmLkwLZSEhIPM7KsZ9HbjfowhAe1wF/hZ1iRDzCjknBu1LZcdQhe5Ptu6T2?iv=C4jXF0j5ldeCO6hv9Zajlg==",
    "created_at":1694705897,
    "id":"9a0cce3a14184cbd575ea8ef5f61caa1da830320ab8222902eeaf701bd20677a",
    "kind":9292,
    "pubkey":"4639e297633117888df17deed6b3860ff152e9e464690623b6b3d6ae4923ad62",
    "sig":"2fb7a6c956b66c3c189e2e9775483270ab95a82a7578d75390ce3e50a4d7b223cbce31402277c48d9f4565a02fbd933e676474eed81d69e32dce94d175406023",
    "tags":[
        ["p","3eea9e831fefdaa8df35187a204d82edb589a36b170955ac5ca6b88340befaa0"],
        ["p","f831caf722214748c72db4829986bd0cbb2bb8b3aeade1c959624a52a9629046"],
        ["e","e534d73109b98a8a2f2627634ab1d0195923dd638b6aa76a63eb7eefa3d59e32"], // Proposal ID
        ["e","9e0dfd2177ea9357f0c165ed134a86a3c07449676d8315e12d159932ff428e37"] // Policy ID
    ]
}
```

## 9094 - Signer

TODO: description

### Example

```json
{
    "content":"bVTA0YYf0+8CZXZtnBWMFu5YLyJR75YyRgAuiATQIvc2LEqiB9B5ARhypbtP+pGRXrhHGaPeZCzSunsP/sb5MXuXmsofAlzWeEAUcAaZC59z2hC97d2DSwYCQFE89MQTf9wrCPZGGAyfEMG9cnSeBuxldKKL5xOPCLfv4JqRSqdILI08h6leaxKTjZLJOLA+Pno7BZlsHazBuV7ZKwq6uGtsF3Nx2v3be+/210JnIrUFyOmCTqatkaLEHLHzekfTV86lJZTQ7YH7XE+TeQpen4H2ZlaJoeEB/JbR8PuONlVo1tjbWq8gdV0G/7kDs57LIzHW6pPsmyh1CNkokfp1Uw==?iv=UUAnvlWtfnHbj5bqDZomhA==",
    "created_at":1688205807,
    "id":"fe1b6712daabae7157b4948d74c53a01f6186c4ecf0619ea147de85fbed8735a",
    "kind":9294,
    "pubkey":"f831caf722214748c72db4829986bd0cbb2bb8b3aeade1c959624a52a9629046",
    "sig":"65783a7e0e1cff481cfc861413a2485ce3e9c461887c51e6258d9e00023a8c34058239f55f2156e88c6052e3df252bdfbc5bd132ebe6773968621ece5517af41",
    "tags":[]
}
```

## 9095 - Shared signer

TODO: description

### Required tags

* `e`: event ID of the `signer`
* `p`: public key of the user to you are sharing signer to

### Example

```json
{
    "content":"LC3wv4bucBHIIQkvR9iNlQbSHlEIRqRnfPM0cDwxYr8NRL57Jq1K6kmUbGPXrviDgYlUiNxxeRYNKqd2OX4vhjojUuUQpSr7B01zSS1nCi7JlJU1BdlNcvwZSN/Qd6cW+fXfBTLebdBVRDAR9N681i0rf1kaRI5v3kcTK/Kgq8YFDun0C85nRjyt1GsfcrH297w9nF1+uG3MXtTXAbh3sDPuEWLFR8MS8OEdjntlgD3VGIiwG+xzFdwwkNosptATp0GEjBQhG3jcccGgG9kUhg==?iv=TwMC14xa7Ux9BK6zyu1Cpw==",
    "created_at":1688207242,
    "id":"1220540b6c8f6d5179cafdae93e304a3cc4134a9d958f7c4094dc985347b5a8d",
    "kind":9295,
    "pubkey":"f831caf722214748c72db4829986bd0cbb2bb8b3aeade1c959624a52a9629046",
    "sig":"e3df3184440dcbdb31f9dc13071e59375480f3f744b25586601d8f646edaf66e8f13699e46ae04683e6a6b26ffbf9a392f1cfee352d4cd13dba223650e63ba52",
    "tags":[
        ["e","fe1b6712daabae7157b4948d74c53a01f6186c4ecf0619ea147de85fbed8735a"], // Signer ID
        ["p","3eea9e831fefdaa8df35187a204d82edb589a36b170955ac5ca6b88340befaa0"]
    ]
}
```

## 32121 - Label

TODO: description

### Required tags

* `e`: event ID of the `vault`
* `d`: unique ID of the `label`
* `p`: public keys of the users involved in the `vault`

### Example

```json
{
    "content":"8pIsvOkUvh2necC9kQuRjDMRyDZPDzvigt/cy7RY+690KUwqT/IluT7+yezIO5i2EG9EyizVFGOn35unILaF3tiquGACLvFy39pSwdZCLdNWQcPWFFn/BPLBW/9j9RJy3UqBr9YHdPABDo4nsdd1Ww==?iv=hl9l3SiUiHss58o4oxi8Dg==",
    "created_at":1694864773,
    "id":"1fd6cbd917c1e2ed2b0b3d18755460e49fbdb1ae46301e68c77747bbbf542244",
    "kind":32121,
    "pubkey":"4639e297633117888df17deed6b3860ff152e9e464690623b6b3d6ae4923ad62",
    "sig":"d88ef25b04104a46d2568084fe268a10518fcb8c1c85999d462389f067ac79ccaec285b84cb2600fedfae04650fd12cdbe070f4b167ca7acd0bc86f4ecb83daa",
    "tags":[
        ["p","3eea9e831fefdaa8df35187a204d82edb589a36b170955ac5ca6b88340befaa0"],
        ["p","f831caf722214748c72db4829986bd0cbb2bb8b3aeade1c959624a52a9629046"],
        ["d","1f7db84fdf986cea2fa1d70f2120ad85"], // Unique ID
        ["e","9e0dfd2177ea9357f0c165ed134a86a3c07449676d8315e12d159932ff428e37"] // Policy ID
    ]
}
```