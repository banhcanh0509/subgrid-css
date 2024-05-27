# Link: [https://banhcanh0509.github.io/subgrid-css](https://banhcanh0509.github.io/subgrid-css)

## Công dụng của Subgrid CSS

-   Căn đều các thành phần trong grid cho toàn bộ grid

## Thực hiện

-   Cho Item có display là `grid`
-   Thêm thuộc tính _**grid-template-rows**_/_**grid-template-columns**_ với giá trị **`subgrid`**
-   Dựa vào tổng số thành phần của **item** và thêm thuộc tính _**grid-row**_ / _**grid-column**_ tương ứng. _Ví dụ Item có 3 thành phần gồm (img, title, desc) thì grid-rows: span 3_

## Trường hợp

### Single element

-   Có nghĩa là 1 Item có phần từ riêng lẻ
-   Dựa vào số lượng thành phần trong Item ta sẽ set cho Item:

    ```css
    /*
        * Căn các Item nằm trên hàng ngang bằng nhau.
        * Item có 3 thành phần
        */

    .item {
        display: grid;
        grid-template-rows: subgrid;
        grid-row: span 3;
    }
    ```

### Subgrid lồng subgrid

-   Có nghĩa là 1 Item có các thành phần và trong đó có 1 thành phần chứa các thành phần con cấp nhỏ hơn.
-   Item sẽ dựa vào tổng các thành phần năm trong.
-   Ví dụ:

    ```css
    /*
    * Item có 2 thành phần image và content. Trong content có thêm 3 thành phần là title, desc và more.
    * Căn các Item nằm trên hàng ngang bằng nhau.
    * Item có tổng cộng 4 thành phần
    * Content có tổng cộng 3 thành phần
    */

    .item {
        display: grid;
        grid-template-rows: subgrid;
        grid-row: span 4;
        /* image + content { title + desc + more }*/
    }

    .content {
        display: grid;
        grid-template-rows: subgrid;
        grid-row: span 3;
        /* content chứa 3 thành phần ( title, desc và more */
    }
    ```
