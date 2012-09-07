# JoystickController

Fully compatible with SparkFun's [Arduino joystick shield](https://www.sparkfun.com/products/9760?). The class lets you easily fetch the current status of the joystick. Implementation is quite simple;

	JoystickController(int low = DEFAULT_LOW, int high = DEFAULT_HIGH)

is a constructor. The first argument specifies the lower threshold value for the directional key pad, below which the controller is assumed to set left/down in the horizontal/vertical direction. The second argument specifies the upper threshold value, above which the controller is assumed to set right/up in the horizontal/vertical direction. If arguments are not specified, the following default values will be used:

	static const int DEFAULT_LOW   = 490;
	static const int DEFAULT_HIGH  = 530;

For more information about the threshold see the following article; [Joystick Shield Quickstart Guide: How do I find the current direction of the joystick?](http://www.sparkfun.com/tutorials/171#direction)

	void update()

must get called in the main loop in order for the class to communicate with the joystick.

	int getDirection()

returns the current direction of the directional keypad as integer values that are defined as class static variables:

	static const int DIRECTION_NONE       = 0;
	static const int DIRECTION_UP         = 1;
	static const int DIRECTION_RIGHT_UP   = 2;
	static const int DIRECTION_RIGHT      = 3;
	static const int DIRECTION_RIGHT_DOWN = 4;
	static const int DIRECTION_DOWN       = 5;
	static const int DIRECTION_LEFT_DOWN  = 6;
	static const int DIRECTION_LEFT       = 7;
	static const int DIRECTION_LEFT_UP    = 8;

Finally buttons' status can be fetched from the following functions:

	bool upButtonPressed()
	bool downButtonPressed()
	bool leftButtonPressed()
	bool rightButtonPressed()

They return true if a button is being pressed, otherwise false.

## License

This project is provided under the terms of the [MIT License](http://www.opensource.org/licenses/mit-license.php).

## Contact

* [http://blog.boreal-kiss.net/](http://blog.boreal-kiss.net/)
* [http://twitter.com/borealkiss](http://twitter.com/borealkiss)