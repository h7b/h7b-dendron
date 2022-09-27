---
id: cf1MgCwuSTEj2lWGsbQG8
title: Highlight
desc: ''
updated: 1639177935769
created: 1638729634163
---
# Notes from reading [[notes.reading.cobol-controls-your-money]]

COBOL programs — some written so long ago that colour TV wasn’t even a thing yet — are everywhere in our daily lives. Over 80% of in-person transactions at U.S. financial institutions use COBOL. Fully 95% of the time you swipe your bank card, there’s COBOL running somewhere in the background.

In 1969, COBOL was was the first language to make computers widely useful for everyday life, which could be possibly compared to no-code movement in the 2020-era.

The Y2K bug emerged from an old design decision. When the early COBOL programmers wrote dates into their software, they used two digits: 1971 was “71”, for example. That was because the machines back in the ’60s and ’70s had very little storage room in their memory. Removing two characters was a big deal. ”All programs were very memory conscious — every byte used to be expensive,” as Thomas tells me. Plus, the coders in the ’60s and ’70s never dreamed their software would still be in use 30 years later, when the year 2000 approached.

But as 2000 drew near, the two-digit dates became a huge dilemma. In the new millennium, the COBOL software wouldn’t know whether “00” meant 2000 or 1900. If a bank calculated interest on a deposit made on “01”, it might wrongly assume the deposit was made in 1901, and issue the customer 99 years of free interest. A huge number of bank and retail and payroll transactions all rely on dates, so billions of lines of programs needed to be updated.

Even so, at Thomas’s bank, they didn’t have time to truly fix the problem. In some cases, banks and firms didn’t actually change the code to use a full four-digit date like “2016”. Instead, they used a hack: a “sliding rule.” They’d pick a year far enough in the future, like 2045, and make it the new breakpoint. So if the COBOL sees a two-digit date that’s greater than 45, it assumes it’s in the 1900s — so, ”87“ means 1987. And if it sees a number lower than 45, it assumes it’s 2000s — so, “33“ means 2033.

This means, as Thomas notes, that the Y2K problem isn’t, for them, entirely fixed. They just kicked the can down the road. Come 2045, they may well be in a panic again.

---
Hello Bố. Con mới đọc thấy bài này thấy thú vị. 

Nội dung nói về ngôn ngữ lập trình Cobol của những năm 1960. Dù đã cũ nhưng vẫn còn được sử dụng trong các ngân hàng ở Mỹ cho đến ngày hôm nay. Bài viết cũng giải thích đơn giản vì sao sự kiện Y2k những năm 2000 lại là 1 lỗi lớn đối với hệ thống máy tính, cũng vì những giới hạn của Cobol mà người sáng tạo ra có lẽ cũng ko nghĩ tới ngôn ngữ này vẫn còn được dùng sau 5 thập kỷ. 

Bài viết này khiến con suy nghĩ rằng những di sản tri thức của thế hệ trước, dù ko còn gây hứng thú với người đi sau, nhưng vẫn đang được sử dụng và tạo ra giá trị. Vậy điều gì sẽ xảy ra khi những người tạo ra và duy trì di sản này dần nghỉ hưu và ít đi? Việc viết lại các tài liệu hướng dẫn và chú giải chi tiết, dù mất thời gian và có vẻ ko hữu ích trong hiện tại, nhưng có lẽ sẽ giúp các thế hệ sau khi cần duy trì những tài sản tri thức như Cobol vậy
