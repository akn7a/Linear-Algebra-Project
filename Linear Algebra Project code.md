# Linear-Algebra-Project
clear,clc
A=imread('/MATLAB Drive/Linear Algebra Project/photos/4 times world champion (mv1).jpg');
X=im2double(rgb2gray(A));
[U,S,V] = svd(X);
subplot(2,1,1), semilogy(diag(S),'k');title('The Signular Values in a Decreasing Order'); grid on
subplot(2,1,2), plot(cumsum(diag(S))/sum(diag(S)),'k'), title ('The Energy of the Signular Values');grid on
r1 = 33;r2 = 43;r3=64;r4=115;
% 33 - His old Formula One number  & Number of fastest laps he achieved
% 43 - first-place winner in Grand Prix races  
% 64 - Total wins in his Formula One career  
% 115 - Podium finishes throughout his career
Xapprox1 = U(:,1:r1)*S(1:r1,1:r1)*V(:,1:r1)';
Xapprox2 = U(:,1:r2)*S(1:r2,1:r2)*V(:,1:r2)';
Xapprox3 = U(:,1:r3)*S(1:r3,1:r3)*V(:,1:r3)';
Xapprox4 = U(:,1:r4)*S(1:r4,1:r4)*V(:,1:r4)';
figure
subplot(2,3,1);imshow(A);title('MAX VERSTAPPEN.: Original');
subplot(2,3,2);imshow(X);title('Gray Scale: r = 256'); 
subplot(2,3,3);imshow(Xapprox1);title(['r=',num2str(r1,'%d'),]);
subplot(2,3,4);imshow(Xapprox2);title(['r=',num2str(r2,'%d'),]);
subplot(2,3,5);imshow(Xapprox3);title(['r=',num2str(r3,'%d'),]);
subplot(2,3,6);imshow(Xapprox4);title(['r=',num2str(r4,'%d'),]);
disp('1. Ali Redha Adnan / 2. Hasan Muhammad Isa / 3. Hussain Salem Hamad');
% Group members:
% 1. Ali Redha Adnan
% 2. Hasan Muhammad Isa
% 3. Hussain Salem Hamad
