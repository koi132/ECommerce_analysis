# Phân Tích Về Thương Mại Điện Tử

## Mô tả dự án

Dự án này phân tích dữ liệu từ sàn thương mại điện tử Olist của Brazil, sử dụng 9 bộ dữ bao gồm: **olist_customers_dataset**, **olist_geolocation_dataset.csv**, **olist_order_items_dataset**, **olist_order_payments_dataset**, **olist_order_reviews_dataset**, **olist_orders_dataset**, **olist_products_dataset**, **olist_sellers_dataset**, **product_category_name_translation**. Mục tiêu là khám phá, làm sạch, phân tích dữ liệu và xây dựng các mô hình dự đoán nhằm hiểu rõ hơn về các yếu tố liên quan cũng như ảnh hưởng đến thương mại điện tử, từ đó đưa ra các kết luận cần thiết và đề xuất các giải pháp nâng cao an toàn.

## Nội dung chính

- **Khám phá và làm sạch dữ liệu:**  
  - Xử lý giá trị thiếu, ngoại lệ, chuẩn hóa kiểu dữ liệu, loại bỏ dữ liệu không hợp lệ đối với từng bộ dữ liệu.
  - Gộp các bộ dữ liệu lại và chọn các cột cần thiết cho dự án phân tích, sau đó tiếp tục xử lý giá trị thiếu, ngoại lệ, chuẩn hóa kiểu dữ liệu, loại bỏ dữ liệu không hợp lệ trên bộ dữ liệu đã được gộp.

- **Phân tích dữ liệu:**  
  - **Phân tích tổng quan**
    - Tổng quan về khách hàng (khách hàng chi tiêu nhiều nhất, tỷ lệ mua nhiều lần, phân loại khách hàng theo khu vực địa lý, tỷ lệ hài lòng, phân phối điểm đánh giá theo nhóm chi tiêu, tổng khách hàng theo thời gian, khách hàng mới và tích lũy theo thời gian)
    - Tổng quan về sản phẩm (tổng doanh thu, sản phẩm đạt top doanh thu, sản phẩm doanh thu thấp nhất, tổng sản phẩm bán theo năm, top sản phẩm có điểm đánh giá trung bình cao nhất).
    - Tổng quan về thanh toán (phân bố hình thức thanh toán, giá trị thanh toán trung bình theo phương thức, phân bố số lần trả góp, tương quan giữa số lần trả góp và thanh toán).
    - Tổng quan về vận chuyển (phân bố thời gian giao hàng, thời gian giao hàng trung bình theo bang, phân tích tình trạng giao hàng).
    - Tổng quan về đánh giá (phân bố điểm đánh giá, thời gian giao hàng trung bình theo điểm đánh giá, top các loại sản phẩm được đánh giá cao nhất và thấp nhất).
  - **Phân tích nghiệp vụ**
    - Doanh thu và biến động theo thời gian (phân tích doanh thu theo thời gian, phân tích đơn hàng theo thời gian, phân tích ảnh hưởng của đơn hàng bị hủy đối với doanh thu, )
    - Sản phẩm và khối lượng bán (phân tích lượng bán theo loại sản phẩm).
    - Khách hàng và hành vi mua hàng (Phân tích việc mua lại của khách hàng, phân tích khách hàng dựa trên hành vi mua, phân tích dựa trên điểm đánh giá trung bình và doanh thu theo mỗi sản phẩm).
    - Người bán và hiệu suất (phân tích người bán hàng theo đơn hàng và doanh thu).
    - Vị trí địa lý (phân bố khách hàng trên các thành phố ở Brazil).
- **Xây dựng mô hình dự đoán:**  
  - Dự đoán dự đoán doanh thu theo ngày bằng XGBoost Regressor.

- **Đánh giá mô hình:**  
  Sử dụng các chỉ số MAE, RMSE, R² để đánh giá mô hình.

## Hướng dẫn sử dụng

- **Cài đặt thư viện cần thiết:**
    ```sh
    pip install pandas numpy matplotlib seaborn holidays statsmodels xgboost scikit-learn
    ```

- **Chạy notebook:**  
   Mở file `ECommerce_analysis.ipynb` trên Jupyter Notebook hoặc VSCode và chạy tuần tự các cell.

## Kết quả nổi bật

- Phân tích dữ liệu đã mang lại cái nhìn sâu sắc và định lượng về hành vi khách hàng, hiệu suất sản phẩm, người bán và xu hướng tiêu dùng theo thời gian. Nếu biết khai thác tốt những dữ liệu này, Olist có thể nâng cao khả năng cá nhân hóa trải nghiệm, tăng doanh thu và duy trì sự phát triển bền vững trên thị trường thương mại điện tử đầy cạnh tranh.

## Đề xuất

1. Chiến lược giữ chân khách hàng:

- Xây dựng chương trình khách hàng thân thiết, tích điểm đổi quà hoặc giảm giá cho đơn hàng kế tiếp.

- Gửi email/đề xuất sản phẩm cá nhân hóa dựa trên lịch sử mua hàng của nhóm khách tiềm năng và trung thành.

2. Cải thiện chất lượng dịch vụ và trải nghiệm:

- Tăng cường kiểm soát chất lượng sản phẩm, đặc biệt với nhóm có nhiều đánh giá thấp.

- Theo dõi sát các trường hợp giao hàng trễ, sản phẩm lỗi → cải thiện vận chuyển và hỗ trợ sau bán.

3. Tối ưu hóa người bán (seller):

- Đánh giá hiệu suất người bán định kỳ, đề xuất hỗ trợ huấn luyện hoặc loại bỏ người bán có tỷ lệ huỷ đơn hoặc đánh giá thấp cao.

- Khuyến khích người bán đạt chuẩn qua chương trình "Người bán uy tín" (badge/highlight).

4. Định hướng sản phẩm và thời điểm bán:

- Tập trung khai thác các nhóm sản phẩm có doanh thu và đánh giá tốt trong các tháng cao điểm (Q4).

- Dự báo nhu cầu và chuẩn bị tồn kho hợp lý cho các dịp lễ.

---


