# AI_tracking
Question 1 (3 points): Exact Inference Observation
- Duyệt từng vị trí hợp lệ:
  + Nếu noisyDistance là none thif pacman đã ăn ma => cập nhật vị trí ma bị ăn. 
  + Nếu không thì cập nhật belief dựa vào khoảng cách từ ma đến vị trí đó.

Question 2 (4 points): Exact Inference with Time Elapse
- Duyệt từng vị trí hợp lệ: lấy phân phối về vị trí ma sẽ đến tiếp theo, cập nhật belief.

Question 3 (3 points): Exact Inference Full Test
- Duyệt các action hợp lệ, lấy vị trí của trạng thái kế tiếp, 
duyệt vị trí của ma livingGhostPositionDistributions, lấy vị trí của ma có khả năng cao nhất, tính khoảng cách 
nếu vị trí đó khác 0, cập nhật giá trị value cho action đó.

Question 4 (3 points): Approximate Inference Observation
- Cài đặt hàm initializeUniformly(self, gameState): liệt kê các vị trí của con ma có thể có, thiết lập các vị trí cụ thể.
- Cài đặt hàm getBeliefDistribution(self): lấy beliefDistribution bằng Couter()
- Cài đặt àm observe(self, observation, gameState):
    + Nếu noisyDistance là none => cập nhật vị trí particle là vị trí ma bị ăn. 
    + Nếu không => cập nhật belief giống như đã implement trong class exactInference.
    
Question 5 (4 points): Approximate Inference with Time Elapse
- Cài đặt hàm elapseTime giống với hàm elapseTime của ExactInference:
Lấy tất cả các vị trí của ma, lấy mẫu vị trí cho 1 số particle.

Question 6 (4 points): Joint Particle Filter Observation
- Cài đặt hàm initializeParticles(self): liệt kê tất cả những vị trí hợp lệ rồi tráo.
- Cài đặt hàm getBeliefDistribution(self): duyệt từng particle trong self.particles, với mỗi giá trị beliefDistribution[particle] cộng thêm 1.0.
- Cài đặt hàm observeState(self, gameState): Nếu số noisyDistances < số ma, với mỗi particleIndex trong range(self.numParticles), duyệt ma trong range(self.numGhosts): 
 + Nếu noisyDistance là none, thì ma sẽ xuất hiện trong ô tù 
 + Nếu không cập nhật lại belief cho mỗi ma. 
 
Question 7 (4 points): Joint Particle Filter with Elapse Time
 - Lấy phân bố vị trí cho, thêm newParticle mẫu lấy từ phân bố vị trí đó.

