
![](../images/ssd1315.pdf-0027-02.png)

- write_i(0x40);    /*set display start line*/ 

- write_i(0xB0);    /*set page address*/ 

- write_i(0x81);    /*contract control*/ write_i(0xb0);    /*128*/ 

- write_i(0xA1);    /*set segment remap*/ 

write_i(0xA4); 

- write_i(0xA6);    /*normal / reverse*/ 

- write_i(0xA8);    /*multiplex ratio*/ 

- write_i(0x3F);    /*duty = 1/64*/ 

- write_i(0xC8);    /*Com scan direction*/ 

- write_i(0xD3);    /*set display offset*/ write_i(0x00); 

write_i(0xD5);    /*set osc division*/ write_i(0x90); 

![](../images/ssd1315.pdf-0027-14.png)

write_i(0xD9);    /*set pre-charge period*/ write_i(0x22); 

write_i(0xDA);    /*set COM pins*/ write_i(0x12); 

write_i(0xdb);    /*set vcomh*/ write_i(0x30); 

write_i(0x8d);    /*set charge pump enable*/ write_i(0x14); 

write_i(0xAF);    /*display ON*/ } 

void write_i(unsigned char  ins) 

{ 

unsigned char  m,da; 

unsigned int j; 

DC=0; 

![](../images/ssd1315.pdf-0027-25.png)

