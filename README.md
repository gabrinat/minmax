# minmax

var
    fin, fout: text;
    max, min, x: longint;
    k: byte;

begin
    max := 0;
    min := 0;
    k := 0;
    assign(fin, 'C:\Users\temp\Desktop\input.txt');
    assign(fout, 'C:\Users\temp\Desktop\output.txt');
    reset(fin);
    rewrite(fout);
    while not eof(fin) do
    begin
        readln(fin, x);
        if (k = 0) and (x mod 2 = 0) and (x > 0) then
        begin
            min := x;
            max := x;
            k := 1;
        end
        else if (x mod 2 = 0) and (x > 0) then
        begin
            if (x > max) then
                max := x;
            if (x < min) then
                min := x;
        end;
    end;
    if (max = 0) then
        writeln(fout, 'max = error')
    else
        writeln(fout, 'max = ', max);
    if (min = 0) then
        writeln(fout, 'min = error')
    else
        writeln(fout, 'min = ', min);
    close(fin);
    close(fout);
end.
