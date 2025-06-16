Simple custom method:

    private void loadFragment(int container, Fragment fragment, int flag)
    {
        FragmentManager fm = getSupportFragmentManager();
        FragmentTransaction ft = fm.beginTransaction();
        if(flag == 0)
            ft.add(container, fragment);
        else
            ft.replace(R.id.container, fragment);
        ft.commit();
    }

Loading default fragment:

        loadFragment(R.id.container, new BFragment(), 0);

Set to Button:

        btnFragA.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                loadFragment(R.id.container, new AFragment(), 1);
            }
        });

        btnFragB.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                loadFragment(R.id.container, new BFragment(), 1);
            }
        });

        btnFragC.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                loadFragment(R.id.container, new CFragment(), 1);
            }
        });

