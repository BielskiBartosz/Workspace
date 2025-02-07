use std::collections::HashMap;

fn main() {
    let mut url_map = HashMap::new();
    url_map.insert("ggl", "https://www.google.com");
    url_map.insert("yt", "https://www.youtube.com");

    println!("Shortened URLs:");
    for (key, url) in &url_map {
        println!("{} -> {}", key, url);
    }

    println!("Enter shortcode:");
    let mut input = String::new();
    std::io::stdin().read_line(&mut input).expect("Failed to read input");
    let input = input.trim();

    match url_map.get(input) {
        Some(url) => println!("Redirecting to: {}", url),
        None => println!("Shortcode not found."),
    }
}
