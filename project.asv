%% Message Signal :
x1 = load('gong');
x2 = load('handel');
x3 = load('laughter');

[s1,n1] = size(x1.y);
[s2,n2] = size(x2.y);
[s3,n3] = size(x3.y);
maxs = max([s1,s2,s3]);
nsms1 = zeros(maxs,1);
nsms2 = zeros(maxs,1);
nsms3 = zeros(maxs,1);

nsms1(1:s1,1) = x1.y;
nsms2(1:s2,1) = x2.y;
nsms3(1:s3,1) = x3.y;

Fc1 = 10000;
Fc2 = 35000;

Fs =100000;
y1 = ammod(nsms1 , Fc1 , Fs , 0);
y2 = ammod(nsms2 , Fc2 , Fs , 0);
y3 = ammod(nsms3 , Fc2 , Fs , pi/2);
y = y1 + y2 + y3 ;

figure
subplot(2, 1, 1);
plot(y,'r');
ylim([-2, 2]);
subplot(2, 1, 2);
plot(abs(fft(y)),'b');

%1 plot y in time ad freq domains%
ffY =abs(fft(y));
%low pass filters %
[nums1 , den1] = butter(10 , Fc1*2/Fs);
[nums2 , den2] = butter(10 , Fc2*2/Fs);
[nums3 , den3] = butter(10 , Fc2*2/Fs);

%demodulated signals%
z1 = amdemod(y , Fc1 , Fs , 0 , 0 , nums1 , den1);
z2 = amdemod(y , Fc2 , Fs , 0 , 0 , nums2 , den2);
z3 = amdemod(y , Fc2 , Fs , pi /2  , 0 , nums3 , den3);

z1_10 = amdemod(y , Fc1 , Fs , pi/18 , 0 , nums1 , den1);
z2_10 = amdemod(y , Fc2 , Fs , pi/18 , 0 , nums2 , den2);
z3_10 = amdemod(y , Fc2 , Fs , (pi /2)+(pi/18)  , 0 , nums3 , den3);

z1_30 = amdemod(y , Fc1 , Fs , pi/6 , 0 , nums1 , den1);
z2_30 = amdemod(y , Fc2 , Fs , pi/6 , 0 , nums2 , den2);
z3_30 = amdemod(y , Fc2 , Fs , (pi /2)+(pi/6)  , 0 , nums3 , den3);

z1_90 = amdemod(y , Fc1 , Fs , pi/2 , 0 , nums1 , den1);
z2_90 = amdemod(y , Fc2 , Fs , pi/2, 0 , nums2 , den2);
z3_90 = amdemod(y , Fc2 , Fs , pi  , 0 , nums3 , den3);

figure 
subplot(2,1,1);
plot(abs(fft(z1_90)))
subplot(2,1,2);
plot(z1)

% % 
% % figure
% % subplot(4, 2, 1);
% % plot(t(1:10000), y(1:10000));
% % title('modulated Signal in time domin');
% % xlabel('time(t)');
% % ylabel('Amplitude');
% % 
% % subplot(4, 2, 2);
% % plot(t(1:10000), ffY(1:10000));
% % title('modulated Signal in freq domin');
% % xlabel('freq(f)');
% % ylabel('Amplitude');
% % 
% % subplot(4, 2, 3);
% % plot(t(1:10000), x1.y(1:10000));
% % title('Message Signal x1');
% % xlabel('time(t)');
% % ylabel('Amplitude');
% % ylim([-2, 2]);
% % 
% % subplot(4, 2, 4);
% % plot(t(1:10000), z1(1:10000));
% % title('demodulated x1');
% % xlabel('time(t)');
% % ylabel('Amplitude');
% % ylim([-2, 2]);
% % 
% % subplot(4, 2, 5);
% % plot(t(1:10000), x2.y(1:10000));
% % title('Message Signal x2');
% % xlabel('time(t)');
% % ylabel('Amplitude');
% % ylim([-2, 2]);
% % 
% % subplot(4, 2, 6);
% % plot(t(1:10000), z2(1:10000));
% % title('demodulated x2');
% % xlabel('time(t)');
% % ylabel('Amplitude');
% % ylim([-2, 2]);
% % 
% % subplot(4, 2, 7);
% % plot(t(1:10000), x3.y(1:10000));
% % title('Message Signal x3');
% % xlabel('time(t)');
% % ylabel('Amplitude');
% % ylim([-2, 2]);
% % 
% % subplot(4, 2, 8);
% % plot(t(1:10000), z3(1:10000));
% % title('demodulated x3');
% % xlabel('time(t)');
% % ylabel('Amplitude');
% % ylim([-2, 2]);
% 

