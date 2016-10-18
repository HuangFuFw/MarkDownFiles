####乱笔记
迭代器：

    public static void main(String[] args) {
        List<String> list = new ArrayList<String>();
        list.add("abc");
        list.add("bbc");
        list.add("cbc");
        for (Iterator<String> it = list.iterator(); it.hasNext(); ) {
            String info = it.next();
            if (info.equals("abc"))
                it.remove();
        }
        System.out.print(list);
    }

