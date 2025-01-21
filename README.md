# Java

package model.com;

public class IntegerStack {
	private int[] data;
    private int top;
    private static final int SIZE = 5;

    public IntegerStack() {
        data = new int[SIZE];
        for (int i = 0; i < SIZE; i++) {
            data[i] = -1;
        }
        top = -1;
        System.out.println("++++ Stack Initialized For " + SIZE + " elements ++++");
        printStack();
    }

    public void push(int element) {
        if (isFull()) {
            System.out.println("Stack Overflow! Cannot push element: " + element);
            return;
        }
        top += 1;
        data[top] = element;
    }

    public int pop() {
        if (isEmpty()) {
            System.out.println("Stack Underflow! Cannot pop element.");
            return -1;
        }
        int element = data[top];
        data[top] = -1;
        top -= 1;
        return element;
    }

    public int peek() {
        if (isEmpty()) {
            System.out.println("Stack is empty! No top element.");
            return -1;
        }
        return data[top];
    }

    public boolean isFull() {
        return top == SIZE - 1;
    }

    public boolean isEmpty() {
        return top == -1;
    }

    public void printStack() {
        System.out.print("Stack elements: ");
        for (int i : data) {
            System.out.print(i + " ");
        }
        System.out.println("\nTOP => " + top);
    }

}




package test.com;

import model.com.IntegerStack;

public class TestStack {
	 public static void main(String[] args) {
	        IntegerStack stack = new IntegerStack();

	        int element = 10;
	        while (!stack.isFull()) {
	            stack.push(element);
	            element += 10;
	        }
	        stack.printStack();

	        System.out.println("++++ STACK FULL ++++");

	        while (!stack.isEmpty()) {
	            element = stack.pop();
	            stack.printStack();
	        }

	        System.out.println("++++ STACK EMPTY ++++");
	    }
}








