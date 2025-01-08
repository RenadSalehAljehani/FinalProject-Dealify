# Dealify | صفقتنا
Delify is an innovative platform that offers users the opportunity to purchase products at discounted prices by gathering a sufficient number of participants for the same deal
#
Key Features:
- For Customers:
1. Track Deals:
      - Monitor active deals and progress.
2. Create or Join Deals:
      - Initiate a new group deal or participate in an existing one.
3. Ratings and Reviews:
      - Rate products, sellers, or other users within the same deal.
      - Evaluate the reliability of users (e.g., flag users who frequently abandon deals).
3. Requests:
      - Submit requests to be removed from the blacklist.
      - Request product returns with a detailed reason.


- For Vendors:
1. Product Management:
     - Add and manage products on the platform.
2. Blacklist Management:
     - Add or remove users from the blacklist.
3. Return Requests:
     - Approve or reject product return requests.
4. Client Reviews:
    - Evaluate and rate clients based on their participation behavior.
  
Dealify connects users and vendors in a unified platform, creating a collaborative shopping experience where group purchasing unlocks exclusive discounts, fostering a thriving community of deal seekers and sellers.
#

# النسخة العربية:

"صفقتنا" هي منصة مبتكرة تتيح للمستخدمين شراء المنتجات بأسعار مخفضة من خلال جمع عدد محدد من المشاركين في نفس الصفقة.

الميزات الرئيسية:
- للعملاء:
1. متابعة الصفقات:
    - متابعة الصفقات النشطة وتقدمها.
2. إنشاء أو الانضمام إلى صفقات:
    - بدء صفقة جماعية جديدة أو المشاركة في صفقة موجودة.
3. التقييمات والمراجعات:
    - تقييم المنتجات أو البائعين أو المستخدمين الآخرين ضمن نفس الصفقة.
    - تقييم موثوقية المستخدمين (مثلًا، الإشارة إلى المستخدمين الذين يتخلفون عن إتمام الصفقات).
4. الطلبات:
    - تقديم طلبات لإزالة المستخدمين من القائمة السوداء.
    - طلب استرجاع المنتجات مع تقديم سبب مفصل.


- للبائعين:
1. إدارة المنتجات:
    - إضافة وإدارة المنتجات على المنصة.
2. إدارة القائمة السوداء:
    - إضافة أو إزالة المستخدمين من القائمة السوداء.
3. طلبات الإرجاع:
    - الموافقة أو الرفض على طلبات إرجاع المنتجات.
4. مراجعات العملاء:
    - تقييم العملاء بناءً على سلوكهم في المشاركة في الصفقات.
  
صفقتنا تربط المستخدمين والبائعين في منصة موحدة، مما يخلق تجربة تسوق تعاونية حيث تتيح الشراء الجماعي الحصول على خصومات حصرية، مما يعزز مجتمعًا مزدهرًا من الباحثين عن الصفقات والبائعين.

#
# Links
- [Figma](https://www.figma.com/design/kUyt9oIMPtgUqbXLnBDkS3/Dealify?node-id=0-1&t=GhXfJIKfyUDjqQfR-1)
- [Presentation](https://www.canva.com/design/DAGbZqlKQ60/OAW5OSI2w2P_I_IUJoBvkQ/edit?utm_content=DAGbZqlKQ60&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
- [PostMan API Documentation](https://documenter.getpostman.com/view/39709967/2sAYJAdGzY)
- ![QR Code](https://github.com/user-attachments/assets/dd59b236-3b36-40fc-91c6-270ec574485a)


#
# Diagrams
UseCase Diagrams:
- ![UseCase](https://github.com/user-attachments/assets/12d485e2-0cf4-4181-8254-3eb917b8670d)


Class Diagram:
- ![Class Diagram](https://github.com/user-attachments/assets/6df6f3d8-4659-480f-b86a-6cc68798e1a8)


# BackEnd:
- Models + CRUD:
1. Category
2. CustomerReview
3. Inventory
4. Product
5. ReturnRequest.

- Repositories:
1. CategoryRepository.
2. CustomerReviewRepository.
3. InventoryRepository.
4. ProductRepository.
5. ReturnRequestRepository.

- Services:
1. CategoryService
2. InventoryService
3. ReturnRequestService

- Controllers:
1. CategoryController
2. CustomerReviewController
3. InventoryController
4. ReturnRequestController

- In & Out DTOs:
1. CustomerReviewInDTO
2. ProductInDTO
3. ReturnRequestCustomerInDTO
4. CategoryOutDTO
5. CustomerReviewOutDTO
6. ProductOutDTO
7. ReturnRequestOutDTO

- JUnit Tests:
1. addCategoryTest()
2. updateCategoryTest()
3. viewProductDealsTest()
4. viewCustomerOpenedDealsTest()
5. viewVendorsOpenDealsTest()

- Extra Endpoints:
1. public ResponseEntity getCategoryByName(@PathVariable String name) {}
2. public ResponseEntity viewDealsByProductCategory(@PathVariable(name = "category-name") String categoryName) {}
3. public ResponseEntity deleteACustomerReview(@AuthenticationPrincipal MyUser myUser, @PathVariable(name = "review-id") Integer ReviewId) {}
4. public ResponseEntity viewProductById(@PathVariable(name = "product-id") Integer productId) {}
5. public ResponseEntity viewProductImages(@PathVariable(name = "product-id") Integer productId) {}
6. public ResponseEntity viewProductsByVendor(@PathVariable(name = "vendor-id") Integer vendorId) {}
7. public ResponseEntity creatReturnRequest(@AuthenticationPrincipal MyUser myUser, @PathVariable Integer productId, @PathVariable Integer dealId, @RequestBody @Valid ReturnRequestCustomerInDTO returnRequestCustomerInDTO) {}
8. public ResponseEntity getVendorReturnRequests(@AuthenticationPrincipal MyUser myUser) {}
9. public ResponseEntity getVendorInventory(@AuthenticationPrincipal MyUser myUser) {}
10. public ResponseEntity getVendorProfileById(@PathVariable(name = "vendor-id") Integer vendorId) {}
11. public ResponseEntity activateVendor(@AuthenticationPrincipal MyUser myUser, @PathVariable(name = "vendor-id") Integer vendorId) {}
12. public ResponseEntity updateProductImages(@AuthenticationPrincipal MyUser myUser, @PathVariable(name = "product-id") Integer productId, @RequestBody @Valid ImageInDTO imageInDTO) {}
13. public ResponseEntity acceptReturnRequest(@AuthenticationPrincipal MyUser myUser, @PathVariable(name = "return-request-id") Integer returnRequestId) {}
14. public ResponseEntity rejectReturnRequest(@AuthenticationPrincipal MyUser myUser, @PathVariable(name = "return-request-id") Integer returnRequestId) {}
