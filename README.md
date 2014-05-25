android-floating-action-menu
============================

Floating Action Menu for Android. Inspired by the Google Plus floating menu.

Demo
====

[![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/mLplXAJ5vug/0.jpg)](https://www.youtube.com/watch?v=mLplXAJ5vug&feature=youtu.be)


Setup
=====

The simplest way to use this library is to add the library as a gradle aar dependency to your build. See the CHANGELOG.md for the latest version number.

	repositories {
    	mavenCentral()
	}

	dependencies {
    	compile 'it.sephiroth.android.library.floatingmenu:floatingmenu:x.x.x' // see changelog
	}

Usage
=====

In your activity create a reference to the `FloatingMenu`:


		FloatingActionItem item1 = new FloatingActionItem.Builder(0)
			.withResId(R.drawable.ic_facebook)
			.withDelay(0)
			.withPadding(action_item_padding)
			.build();

		FloatingActionItem item2 = new FloatingActionItem.Builder(1)
			.withResId(R.drawable.ic_googleplus)
			.withDelay(50)
			.withPadding(action_item_padding)
			.build();

		FloatingActionItem item3 = new FloatingActionItem.Builder(2)
			.withResId(R.drawable.ic_twitter)
			.withDelay(100)
			.withPadding(action_item_padding)
			.build();

		mFloatingMenu = new FloatingActionMenu
			.Builder(this)
			.addItem(item1)
		    .addItem(item2)
			.addItem(item3)
			.withScrollDelegate(new FloatingActionMenu.AbsListViewScrollDelegate(mListView))
			.withThreshold(R.dimen.float_action_threshold)
			.withGap(R.dimen.float_action_item_gap)
			.withHorizontalPadding(R.dimen.float_action_h_padding)
			.withVerticalPadding(R.dimen.float_action_v_padding)
			.withGravity(FloatingActionMenu.Gravity.CENTER_HORIZONTAL | FloatingActionMenu.Gravity.BOTTOM)
			.withDirection(FloatingActionMenu.Direction.Vertical)
			.animationDuration(300)
			.animationInterpolator(new OvershootInterpolator())
			.visible(visible)
		    .build();

		mFloatingMenu.setOnItemClickListener(this);