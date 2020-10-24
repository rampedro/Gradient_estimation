im = imread("vvv.jpeg");
imshow(im)
grayim = rgb2gray(im);
%grayim = double(grayim);
s = 10;
sigma = s;



m = 3*s;

std = sigma;

% create the grid of (x,y) values
%siz = (siz-1)./2;
%m = (m-1)./(6);

%x = meshgrid(-m:1:m);
x = linspace(-m,m,6*s+1);
y = linspace(-m,m,6*s+1);
y = y';

hx = normpdf(x,0,s);
hy = normpdf(y,0,s);


plot(x,hx)
title("X")

plot(y,hy)
title("Y")



sum(hx);

%hx = hx./sum(hx)

sum(hx)

%x;


%N=3*s;M=3*s;dN=1;dM=1;
%[xx,yy]=meshgrid([-m:6.5:m],[-m:6.5:m])
%sum(xx,"all")

% analytic function
%h = exp(-(x.*x + y.*y)/(2*std*std));
%d=0;
%distx =(x-d).*(x-d);
%disty = (y-d).*(y-d);


%hx = exp(-(distx)/(2*std^2))
%hx =  fspecial('gaussian',[1,10],3*s)
%hxSum = sum(hx);
%hy = exp(-(disty)/(2*std^2));
%hx = hx./(sigma*sqrt(pi*2));

% truncate very small values to zero
%hx(hx>3*sigma) = 0;
%hx(hx<(-3*sigma)) = 0;

%hy(disty>3*sigma) = 0;
%hy(disty<(-3*sigma)) = 0;



%jj = conv2(hx,[-1 1],'same');
%jj


% Finding the derivative in X and Y directions 

dhx = hx./(sigma^2);
dhx = dhx.*(-x);

dhy = hy./(sigma^2);
dhy = dhy.*(-y);


%dhx = conv2(hx,[1,-1],'same')
dhx_sum = sum(dhx,'all')
%dhx = dhx./dhx_sum;

plot(x,dhx)
title("derivative X")

plot(y,dhy)
title("derivative Y")


%dhx  = repmat(dhx,6*s+1,1)


%sum_dhx = sum(sum(dhx))

%dev = conv2(hx, [1/2 0 -1/2]);
%devxSum = sum(dev,"all");
%if sumhx ~= 0
%    hx = hx/sumhx;
%end
%hx = hx/sum(hx(:));
%dhx = hx/(sigma^3*sqrt(pi*2));



%dhx = dhx.*(-x);

%dhx;


%hy = hy./(sigma^3*sqrt(pi*2));
%hy = hy.*(-y);

%if sumhy ~= 0
%    hy = hy/sumhy;
%end



%kernalx = kernalx/sumx;
%kernaly = kernaly/sumy;

%hx=fspecial('gaussian',[1 siz(2)],sigma);
%hx=repmat(hx,10);
%dev(dev>3*sigma) = 0;
%dev(dev<(-3*sigma)) = 0;
%g_y=fspecial('gaussian',[yourFilterSize(1) yourFilterSize(2)],sigma);

%hx = conv2(hx,[1,0,-1],"full");

temp1 = grayim;
temp2 = grayim;
g1x = conv2(hx,dhx,temp1,'same');
g1y = conv2(dhy,hy,temp2,'same');

%g1y = conv2(grayim,hy,'same');
%g1x = conv2(hx(:)*hy(:).', grayim)

g1x
g1y


mag = g1x.^2 + g1y.^2;

hmag = sqrt(mag);

g1mag = hmag;


figure(1);
imshow(g1x,[]);
