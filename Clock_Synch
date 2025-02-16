module dfs (
  clk1, //source clk
  clk2, //destination clk
  rst1,
  rst2,
  din,  //input
  dout  //synchronized output
  );

input clk1,clk2,rst1,rst2,din;
output dout;
reg dout, din_flop;
reg dmeta;

always@(posedge clk1 or negedge rst1)
  if(!rst1) din_flop <= 1'b0;
  else din_flop <= din;

always@(posedge clk2 or negedge rst2)
begin
  if(!rst2) 
  begin
    dmeta <= 1'b0;
    dout  <= 1'b0;
  end
  else
  begin 
    dmeta <= din_flop;
    dout  <= dmeta;
  end
end
endmodule
