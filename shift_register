module shift_register #(
    parameter N = 4
)(
    input clk,
    input reset,
    input load,
    input shift,
    input [N-1:0] parallel_in,
    input serial_in,
    output reg [N-1:0] q
);

always @(posedge clk or posedge reset)
begin
    if (reset)
        q <= {N{1'b0}};

    else if (load)
        q <= parallel_in;

    else if (shift)
        q <= {serial_in, q[N-1:1]};
end

endmodule
