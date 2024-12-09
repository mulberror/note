---
title: "CS162 Homework 2: Shell"
---

## Program Execution

使用 `tokenizer.h` 中的代码，

## Redirection

Be aware that < [file] or > [file] are not passed as arguments to the program (i.e. you will not find these characters in the argv argument of the main function in shell.c).

我一开始将这个问题想复杂了，使用 `pipe` 的方法来完成了，一开始的思路是这个前面的输入流要传给后面的程序。

但是其实实际上本身只有一个程序，所以只需要将输入输出重定向到文件就可以了。

```c
int pipefd[2];
if (pipe(pipefd) == -1) {
  perror("pipe");
  exit(1);
}
pid = fork();
if (pid == -1) {
  perror("fork");
  exit(1);
}
if (pid == 0) {
  FILE *input_file = NULL, *output_file = NULL;
  if (input_filename != NULL) {
    input_file = fopen(input_filename, "r");
    if (input_file == NULL) {
      perror("open input file");
      exit(1);
    }
    int input_fd = fileno(input_file);
    dup2(input_fd, STDIN_FILENO);
    fclose(input_file);
  }
  if (output_filename != NULL) {
    output_file = fopen(output_filename, "w");
    if (output_file == NULL) {
      perror("open output file");
      exit(1);
    }
    int output_fd = fileno(output_file);
    dup2(output_fd, STDOUT_FILENO);
    fclose(output_file);
  }

  prog_exec(prog_path, args);
  perror("program exec");
  exit(1);
}
wait(NULL);
return 0;
```